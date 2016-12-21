---
title: "소멸자 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ 연산자, 소멸자 지정"
  - "개체 제거, 소멸자"
  - "소멸자, 소멸자 정보"
  - "소멸자, C++"
  - "개체[C++], 소멸"
  - "Visual C++, 소멸자"
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 소멸자 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"소멸자" 함수는 생성자 함수의 역함수입니다.  이러한 함수는 개체가 소멸될 때\(할당이 해제될 때\) 호출됩니다.  클래스 이름 앞에 물결표\(`~`\)를 사용하여 함수를 클래스의 소멸자로 지정합니다.  예를 들어 클래스 `String`의 소멸자는 `~String()`으로 선언됩니다.  
  
 \/clr 컴파일에서 소멸자는 관리 및 비관리 리소스를 해제하는 특수 역할을 갖습니다.  자세한 내용은 [Visual C\+\+의 소멸자 및 종료자](../misc/destructors-and-finalizers-in-visual-cpp.md)를 참조하세요.  
  
 소멸자는 더 이상 필요 없는 개체를 "정리"하는 데 주로 사용됩니다.  다음 `String` 클래스 선언을 참조하세요.  
  
```  
// spec1_destructors.cpp  
#include <string.h>  
  
class String {  
public:  
   String( char *ch );  // Declare constructor  
   ~String();           //  and destructor.  
private:  
   char    *_text;  
   size_t  sizeOfText;  
};  
  
// Define the constructor.  
String::String( char *ch ) {  
   sizeOfText = strlen( ch ) + 1;  
  
   // Dynamically allocate the correct amount of memory.  
   _text = new char[ sizeOfText ];  
  
   // If the allocation succeeds, copy the initialization string.  
   if( _text )  
      strcpy_s( _text, sizeOfText, ch );  
}  
  
// Define the destructor.  
String::~String() {  
   // Deallocate the memory that was previously reserved  
   //  for this string.  
   if (_text)  
      delete[] _text;  
}  
  
int main() {  
   String str("The piper in the glen...");  
}  
```  
  
 위 예제에서 소멸자 `String::~String`은 `delete` 연산자를 사용하여 텍스트 저장소에 동적으로 할당된 공간을 할당 해제합니다.  
  
## 소멸자 선언  
 소멸자는 클래스와 이름이 같지만 물결표\(`~`\)가 앞에 붙어 있는 함수입니다.  
  
 구문의 첫 번째 형태는 클래스 선언 내부에서 선언되거나 정의된 소멸자에 사용되고, 두 번째 형태는 클래스 선언 외부에서 정의된 소멸자에 사용됩니다.  
  
 몇 가지 규칙이 소멸자의 선언에 적용됩니다.  소멸자는 다음과 같습니다.  
  
-   인수를 받아들이지 않습니다.  
  
-   반환 형식\(`void` 포함\)을 지정할 수 없습니다.  
  
-   `return` 문을 사용하여 값을 반환할 수 없습니다.  
  
-   **const**, `volatile` 또는 **static**으로 선언될 수 없습니다.  하지만 **const**, `volatile` 또는 **static**으로 선언된 개체의 소멸을 위해 호출될 수 있습니다.  
  
-   **virtual**로 선언될 수 있습니다.  가상 소멸자를 사용하면 개체의 형식을 모르는 상태에서 개체를 소멸시킬 수 있습니다. 가상 함수 메커니즘을 사용하여 개체에 대한 올바른 소멸자가 호출됩니다.  소멸자는 추상 클래스의 순수 가상 함수로 선언될 수도 있습니다.  
  
## 소멸자 사용  
 다음 이벤트 중 하나가 발생하면 소멸자가 호출됩니다.  
  
-   **new** 연산자를 사용하여 할당된 개체는 **delete** 연산자를 사용하여 명시적으로 할당 해제됩니다.  **delete** 연산자를 사용하여 개체를 할당 해제하면 메모리에서 "가장 많이 파생된 개체"나 완전한 개체이며, 기본 클래스를 나타내는 하위 개체는 아닌 개체에 대한 공간이 비워집니다.  이 "가장 많이 파생된 개체" 할당 해제는 가상 소멸자의 경우에만 작동하도록 보장됩니다.  형식 정보가 실제 개체의 기본 형식에 대응하지 않는 다중 상속 상황에서는 할당 해제가 실패할 수 있습니다.  
  
-   블록 범위가 있는 로컬\(자동\) 개체는 범위를 벗어납니다.  
  
-   임시 개체의 수명이 종료됩니다.  
  
-   프로그램이 종료되고 전역 또는 정적 개체가 존재합니다.  
  
-   소멸자는 소멸자 함수의 정규화된 이름을 사용하여 명시적으로 호출됩니다.  자세한 내용은 [명시적 소멸자 호출](../misc/explicit-destructor-calls.md)을 참조하세요.  
  
 위 목록에서 설명하는 경우에서는 모든 개체가 사용자 정의 메서드를 사용하여 소멸될 수 있는지 확인합니다.  
  
 기본 클래스 또는 데이터 멤버에 액세스할 수 있는 소멸자가 있고 파생 클래스가 소멸자를 선언하지 않으면 컴파일러가 소멸자를 만듭니다.  이 컴파일러에서 생성된 소멸자가 기본 클래스 소멸자와 파생 형식의 멤버에 대한 소멸자를 호출합니다.  기본 소멸자는 공용입니다.  접근성에 대한 자세한 내용은 [기본 클래스에 대한 액세스 지정자](../misc/access-specifiers-for-base-classes.md)를 참조하세요.  
  
 소멸자는 클래스 멤버 함수를 자유롭게 호출하고 클래스 멤버 데이터에 액세스할 수 있습니다.  소멸자에서 가상 함수를 호출하면 호출된 함수는 현재 소멸되고 있는 클래스에 대한 함수입니다.  자세한 내용은 [소멸 순서](../misc/order-of-destruction.md)를 참조하세요.  
  
 소멸자 사용에 대해 두 가지 제한 사항이 있습니다.  첫 번째 제한은 소멸자의 주소를 가져올 수 없다는 것입니다.  두 번째 제한은 파생 클래스가 기본 클래스의 소멸자를 상속하지 않는다는 것입니다.  대신 이전에 설명한 대로 소멸자는 항상 이러한 기본 클래스의 소멸자를 재정의합니다.  
  
## 소멸 순서  
 개체가 범위에서 벗어나거나 삭제될 때 완전한 소멸에서 발생하는 이벤트 시퀀스는 다음과 같습니다.  
  
1.  클래스의 소멸자가 호출되고 소멸자 함수의 본문이 실행됩니다.  
  
2.  비정적 멤버 개체의 소멸자가 클래스 선언에 나타나는 순서와 반대로 호출됩니다.  이러한 멤버의 생성에 사용된 선택적 멤버 초기화 목록은 생성 또는 소멸 순서에 영향을 주지 않습니다.  멤버 초기화에 대한 자세한 내용은 [기본 항목 및 멤버 초기화](http://msdn.microsoft.com/ko-kr/2f71377e-2b6b-49da-9a26-18e9b40226a1)를 참조하세요.  
  
3.  비가상 기본 클래스의 소멸자가 선언과 반대 순서로 호출됩니다.  
  
4.  가상 기본 클래스의 소멸자가 선언과 반대 순서로 호출됩니다.  
  
```  
// order_of_destruction.cpp  
#include <stdio.h>  
  
struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };  
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };  
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };  
  
struct B1      { ~B1() { printf("B1 dtor\n"); } };  
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };  
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };  
  
int main() {  
   A1 * a = new A3;  
   delete a;  
   printf("\n");  
  
   B1 * b = new B3;  
   delete b;  
   printf("\n");  
  
   B3 * b2 = new B3;  
   delete b2;  
}  
  
Output: A3 dtor  
A2 dtor  
A1 dtor  
  
B1 dtor  
  
B3 dtor  
B2 dtor  
B1 dtor  
  
```  
  
### 가상 기본 클래스  
 가상 기본 클래스의 소멸자는 방향이 있는 비순환 그래프\(깊이 우선, 왼쪽에서 오른쪽으로, 후위 운행법\)에서 표시되는 역순으로 호출됩니다.  다음 그림은 상속 그래프를 보여 줍니다.  
  
 ![가상 기본 클래스를 보여 주는 상속 그래프](../cpp/media/vc392j1.png "vc392J1")  
가상 기본 클래스를 보여 주는 상속 그래프  
  
 다음은 그림에 표시된 클래스의 클래스 헤드를 나열합니다.  
  
```  
class A  
class B  
class C : virtual public A, virtual public B  
class D : virtual public A, virtual public B  
class E : public C, public D, virtual public B  
```  
  
 `E` 형식 개체의 가상 기본 클래스를 파괴하는 순서를 결정하기 위해 컴파일러는 다음 알고리즘을 적용하여 목록을 빌드합니다.  
  
1.  그래프에서 가장 깊은 지점에서 시작하여 왼쪽으로 그래프를 이동합니다\(이 경우 `E`\).  
  
2.  모든 노드를 방문할 때까지 왼쪽으로 이동을 수행합니다.  현재 노드의 이름입니다.  
  
3.  이전 노드\(아래 및 오른쪽으로\)를 다시 방문하여 기억된 노드가 가상 기본 클래스인지 확인합니다.  
  
4.  기억된 노드가 가상 기본 클래스인 경우 목록을 검색하여 이미 입력되었는지를 확인합니다.  가상 기본 클래스가 아닌 경우 무시합니다.  
  
5.  기억된 노드가 아직 목록에 없는 경우 목록의 아래에 추가합니다.  
  
6.  그래프를 위로 이동하고 다음 경로를 따라 오른쪽으로 이동합니다.  
  
7.  2단계로 이동합니다.  
  
8.  마지막 상향 경로가 모두 사용되면 현재 노드의 이름을 참고합니다.  
  
9. 3단계로 이동합니다.  
  
10. 아래쪽 노드가 다시 현재 노드가 될 때까지 이 프로세스를 계속합니다.  
  
 따라서 `E` 클래스의 경우 소멸의 순서는 다음과 같습니다.  
  
1.  비가상 기본 클래스 `E`.  
  
2.  비가상 기본 클래스 `D`.  
  
3.  비가상 기본 클래스 `C`.  
  
4.  가상 기본 클래스 `B`.  
  
5.  가상 기본 클래스 `A`.  
  
 이 프로세스는 고유 항목의 순서 지정된 목록을 만듭니다.  클래스 이름은 두 번 표시되지 않습니다.  목록이 생성되면 역순으로 나타나고 목록의 마지막에서 처음의 순으로 각 클래스에 대한 소멸자가 호출됩니다.  
  
 생성 또는 소멸의 순서는 주로 한 클래스의 생성자 또는 소멸자가 처음으로 만들어진 다른 구성 요소 또는 더 오래 지속되는 다른 구성 요소에 의존하는 경우 중요합니다. 예를 들어 `A`\(위 그림에 표시됨\)의 소멸자가 해당 코드 실행 중 계속 존재하는 `B`에 의존하는 경우가 해당합니다. 반대의 경우도 마찬가지입니다.  
  
 나중에 파생 클래스가 생성과 소멸의 순서를 변경할 수 있는 가장 왼쪽 경로를 변경할 수 있기 때문에 상속 그래프에서 클래스 사이의 이러한 상호 의존성은 본질적으로 위험합니다.  
  
### 비가상 기본 클래스  
 비가상 기본 클래스의 소멸자는 기본 클래스 이름이 선언된 순서와 반대로 호출됩니다.  다음과 같은 클래스 선언을 생각해 보세요.  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 위의 예제에서 `Base2`의 소멸자가 `Base1`의 소멸자보다 먼저 호출됩니다.  
  
## 명시적 소멸자 호출  
 대부분의 경우 소멸자를 명시적으로 호출할 필요가 없지만  절대 주소에 있는 개체를 정리할 때는 도움이 됩니다.  주로 배치 인수를 사용하는 사용자 정의 **new** 연산자를 사용하여 이 개체를 할당합니다.  사용 가능한 저장소에서 할당되지 않으므로 **delete** 연산자가 이 메모리를 할당 해제할 수 없습니다. 자세한 내용은 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.  그러나 소멸자를 호출하면 적절한 정리를 수행할 수 있습니다.  `s` 클래스의 `String` 개체에 대해 소멸자를 명시적으로 호출하려면 다음 문 중 하나를 사용하세요.  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 앞에 나온 대로 소멸자를 정의하는 형식에 관계없이 소멸자를 명시적으로 호출하기 위한 표기법을 사용할 수 있습니다.  그러면 형식에 대해 소멸자가 정의되었는지 여부를 몰라도 명시적인 호출이 가능합니다.  소멸자가 정의되지 않은 경우 명시적 호출은 아무 효과가 없습니다.  
  
## 참고 항목  
 [특수 멤버 함수](../misc/special-member-functions-cpp.md)