---
title: "방법: 예외 안전성을 위한 디자인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 예외 안전성을 위한 디자인
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

예외에 대한 데이터와 함께 해당 실행 예외 메커니즘의 장점 중 하나는, 점프에서 첫 번째 예외를 throw 하는 문 및 직접 catch 문을 처리 하는 것입니다.  처리기는 호출 스택 수준 위의 수일 수 있습니다.  Throw 문과 try 문 사이의 호출 된 함수는 throw 되는 예외에 대한 지식이 필요하지 않습니다.  그러나 디자인 되어서 "갑자기" 밖으로 이동하여 예외가 아래에서 위로 전파 될 수 있고 부분적으로 만들어진된 오브젝트, 메모리 누수 방치, 사용할 수 없는 상태에 있는 데이터 구조를 예방할 수 있습니다.  
  
## 기본 기술  
 강력한 예외 처리 정책은 신중한 생각과 설계 프로세스의 일부를 필요로 합니다.  일반적으로 대부분의 예외를 검색하여 소프트웨어 모듈의 하위 계층에서 throw 됩니다. 하지만 일반적으로 이러한 레이어는 최종 사용자에게 메시지를 표시하거나 오류를 처리할 충분한 컨텍스트를 가지지 않습니다.  중간 계층에서 함수는 예외 개체를 검사할 때나 추가적인 유용한 정보를 상위 계층에 제공하기 위한 유용한 추가 정보가 있는 경우에 catch하거나 예외를 다시 내보낼 수 있습니다.  함수는 catch 하고 완전히 복구할 수 경우에 예외를 "무시" 합니다.  대부분의 경우는 중간 계층에서 올바른 동작은 예외를 호출 스택에서 퍼뜨리는 것입니다.  심지어 최상위 계층에서 예외가 처리되지 않은 경우는 그 정확성을 보장할 수 없는 상태에서 프로그램을 벗어날 경우 프로그램을 종료하는 적절 한 수가 있습니다.  
  
 예외를 처리하는 방법에 관계 없이 "예외 안전"을 보장하기 위해서는 다음과 같은 기본 규칙에 따라 설계 되어야 합니다.  
  
### 리소스 클래스를 간단하게 유지  
 수동 리소스를 관리를 클래스에서 캡슐화 할때 각 리소스를 관리함에 있어서 아무 것도 하지 않는 클래스를 사용하세요. 그렇지 않으면 누수가 발생할 수도 있습니다.  [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 를 가능 하면 다음 예제와 같이 사용하세요.  이 예제는 의도적이고 부적절하며 `shared_ptr` 가 사용 될 때의 차이점을 강조 표시하는 단순한 경우입니다.  
  
```cpp  
// old-style new/delete version  
class NDResourceClass {  
private:  
    int*   m_p;  
    float* m_q;  
public:  
    NDResourceClass() : m_p(0), m_q(0) {  
        m_p = new int;  
        m_q = new float;  
    }  
  
    ~NDResourceClass() {  
        delete m_p;  
        delete m_q;  
    }  
    // Potential leak! When a constructor emits an exception,   
    // the destructor will not be invoked.     
};  
  
// shared_ptr version  
#include <memory>  
  
using namespace std;  
  
class SPResourceClass {  
private:  
    shared_ptr<int> m_p;  
    shared_ptr<float> m_q;  
public:  
    SPResourceClass() : m_p(new int), m_q(new float) { }  
    // Implicitly defined dtor is OK for these members,   
    // shared_ptr will clean up and avoid leaks regardless.  
};  
  
// A more powerful case for shared_ptr  
  
class Shape {  
    // ...  
};  
  
class Circle : public Shape {  
    // ...  
};  
  
class Triangle : public Shape {  
    // ...  
};  
  
class SPShapeResourceClass {  
private:  
    shared_ptr<Shape> m_p;  
    shared_ptr<Shape> m_q;  
public:  
    SPShapeResourceClass() : m_p(new Circle), m_q(new Triangle) { }  
};  
  
```  
  
### 리소스 관리를 위해 RAII 방법을 사용하세요.  
 예외로부터 안전하게 되도록 하기 위해서는 함수가 `malloc` 또는 `new` 를 사용하여 할당 된 개체가 소멸되며 예외가 발생했을지라도 파일 핸들 같은 리소스를 모두 닫거나 출시 된다는 것을 확실히 해야 합니다.  *리소스 인식 Is 초기화* \(RAII\) 방법은 자동 변수의 수명에 해당하는 리소스의 관리를 연결합니다.  함수가 정상적으로 반환 하거나, 예외로 인해 범위를 벗어날 때 완전히 구축된 자동 변수에 대한 소멸자가 호출 됩니다.  스마트 포인터와 같은 RAII 래퍼 개체는 적절한 삭제를 호출하거나 소멸자에서 함수를 닫습니다.  예외 로부터 안전한 코드에서 RAII 개체의 일종으로 각 리소스 소유권을 즉시 전달하는 것이 매우 중요합니다.  `vector`, `string`, `make_shared`, `fstream`과 유사한 클래스 처리에 대한 리소스를 확보하는 것을 확인하세요. 그러나 `unique_ptr` 및 전통적인 `shared_ptr` 구조는 특별합니다. 왜냐하면 리소스 획득이 개체 대신 사용자에 의해 수행 되기 때문입니다. 따라서 RAII와 같이 질문의 여지가 있지만 *리소스 릴리스 Is 파괴* 와 같이 카운트합니다.  
  
## 세 가지 예외 보장  
 일반적으로 예외 안전은 함수를 제공할 수 있는 설명에 있어서 세 가지 예외 보장 측면에서 논의 됩니다. 예를 들어 *장애 없음 보장*, *강력한 보장*, 및 *기본 보장*이 있습니다.  
  
### 무 실패 보장  
 무\-실패 \(또는 "throw"\) 보장은 함수가 제공할 수 있는 가장 강력한 보장입니다.  이 것에 따르면 함수가 예외를 throw 하거나 전파되는 것을 허용하지 않을 것입니다.  그러나 사용자는 다음과 같이 \(a\) 이 함수를 호출하는 모든 함수는 무\-실패 또는 \(b\) 알고 있는 모든 throw 된 예외는이 함수에 도달 하기 전에 또는 catch 되고 이 함수를 연결할 수 있는 모든 예외를 올바르게 처리 하는 방법을 아는 경우 \(c\) 하면 이러한 보장에 제공하는 경우그러한 보장을 쉽게 제공하지 못합니다.  
  
 강력한 보장 및 기본 보장은 소멸자가 무\-실패라는 가정에 의존 합니다.  모든 컨테이너와 표준 라이브러리의 형식은 해당 소멸자가 throw 하지 않는 것을 보장 합니다.  반대 요구가 또한 있습니다. 또한 표준 라이브러리는 사용자 정의 형식들이\-예를 들어 템플릿 인수를 갖는것\-throwing하지 않은 소멸자를 가져야 합니다.  
  
### 강력한 보장  
 강력한 보장 상태는 예외로 인해 함수가 범위를 벗어날 경우 그 것은 메모리를 노출하지 않고 프로그램 상태를 수정할 수 없다는 것을 말해줍니다.  강력한 보장을 제공 하는 함수는 본질적으로 커밋 또는 롤백 의미 체계가 있는트랜잭션입니다. 완전히 성공하거나 영향을 주지 않습니다.  
  
### 기본적인 보장  
 기본 보장은 세가지 중 가장 약합니다.  그러나 강력한 보장이 메모리 소모량이나 성능면에서 너무 비싼 경우 가장 좋은 선택일 수 있습니다.  기본 보장 상태는 만일 예외가 발생하면 메모리 누수가 없으며 데이터가 수정된 경우라도 개체가 여전히 사용 가능한 상태라는 것이라는 것을 보여줍니다.  
  
## 안전 예외 클래스  
 클래스는 부분적으로 파괴되거나 부분적으로 생성되는 것을 스스로 방지하거나 안전하지 않은 함수에 의해 사용되는 경우라도 자체적으로 예외 안정성을 보장하는데 도움이 됩니다.  클래스 생성자가 완료 되기 전에 종료되는 경우 개체는 절대로 만들어지지 않고 해당 소멸자는 절대 호출 되지 않습니다.  예외 이전에 초기화된 자동 변수가 자기만의 소멸자를 가질지라도 스마트 포인터에 의해 관리되지 않는 리소스 또는 자동 변수의 누수가 발생 합니다.  
  
 기본 제공 형식은 모두 무\-실패이고 표준 라이브러리 형식은 최소한 기본 보장을 지원 합니다.  다음 예외 안전이어야 하는 모든 사용자 정의 형식에 대한 이 지침을 따르세요.  
  
-   스마트 포인터 또는 다른 RAII 형식의 래퍼를 사용하여 모든 리소스를 관리하세요.  클래스 소멸자에서 리소스 관리 기능을 지원하지 않습니다. 왜냐하면 생성자가 예외를 나타내는 경우 소멸자는 호출 되지 것이기 때문입니다.  그러나 클래스가 하나의 리소스를 제어 하는 전용된 리소스 관리자라면 다음 경우 소멸자를 사용하여 리소스를 관리할 수 있습니다.  
  
-   기본 클래스 생성자에서 나온 예외가 파생된 클래스 생성자에서 무시될 수 없음을 이해하세요.  파생된 생성자에서 기본 클래스 예외를 다시 throw 하려면 함수 try 블록을 사용합니다.  자세한 내용은 [\(NOTINBUILD\)How to: Handle Exceptions in Base Class Constructors \(C\+\+\)](http://msdn.microsoft.com/ko-kr/53bb822e-785b-4581-9517-210dd05060a3)을 참조하십시오.  
  
-   모든 클레스 상태를 특히 클래스가 "실패하기 위한 초기화."의 개념에 가진 경우 스마트 포인터에 랩된 데이터 멤버에 저장할지 고려하세요. 비록 C\+\+ 에서 초기화 되지 않은 데이터 멤버를 허락할지라도 초기화 되지 않았거나 부분적으로 초기화된 클래스 인스턴스는 지원하지 않습니다.  생성자는 성공하거나 실패합니다; 생성자가 완료 될 때까지 실행 되지 않으면 개체가 만들어지지 않습니다.  
  
-   소멸자에서 벗어나는 예외를 허용 하지 않습니다.  C\+\+의 기본 공리는 소멸자가 호출 스택 위쪽으로 전파하는 예외를 허용 해선 안된다는 것입니다.  소멸자가 잠재적 예외를 throw 하는 작업을 수행해야 한다면 try catch 블록에서 해야하고 예외를 무시합니다.  표준 라이브러리는 정의하는 모든 소멸자에서 보증을 제공합니다.  
  
## 참고 항목  
 [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [방법: 예외 코드와 예외가 아닌 코드 간 인터페이스](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)