---
title: "선언 및 정의 (C++) | Microsoft Docs"
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
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 선언 및 정의 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[선언](http://msdn.microsoft.com/ko-kr/2fd0cddb-b64c-4c9f-9aac-9f8e7ef892f4)은 프로그램 내의 이름\(예: 변수, 네임스페이스, 함수 및 클래스의 이름\)을 소개합니다.  또한, 선언은 형식 정보뿐만 아니라 선언되는 개체의 다른 특성도 지정합니다.  이름은 먼저 선언해야 사용할 수 있습니다. C\+\+에서는 이름이 선언되는 지점에 따라 이름이 컴파일러에 표시되는지 여부가 달라집니다.  컴파일 단위에서 늦은 지점에 선언한 함수 또는 클래스는 참조할 수 없습니다. 이 제한을 해결하려면 *정방향 선언*을 사용하면 됩니다.  
  
 [정의](http://msdn.microsoft.com/ko-kr/f96e2c0d-abb5-4414-9ea1-4d5b4048d50a)는 이름이 설명하는 코드 또는 데이터를 지정합니다.  선언할 항목을 위한 저장소 공간을 할당하려면 컴파일러에 정의가 있어야 합니다.  
  
## 선언  
 선언은 프로그램에 하나 이상의 이름을 제공합니다.  선언은 프로그램에서 두 번 이상 발생할 수 있습니다.  따라서 클래스, 구조체, 열거 형식 및 다른 사용자 정의 형식이 각 컴파일 단위에 대해 선언될 수 있습니다.  이 여러 선언에 대한 제약 조건은 모든 선언이 동일해야 한다는 것입니다.  다음 경우를 제외하고 선언은 정의 역할도 합니다.  
  
1.  선언이 함수 프로토타입\(함수 본문이 없는 함수 선언\)입니다.  
  
2.  선언이 `extern` 지정자를 포함하지만 이니셜라이저\(개체 및 변수\) 또는 함수 본문\(함수\)은 포함하지 않습니다.  이것은 정의가 반드시 현재 변환 단위에 있지 않으며 이름 외부 링크를 제공해 줌을 나타냅니다.  
  
3.  선언이 클래스 선언 내의 정적 데이터 멤버입니다.  
  
     정적 클래스 데이터 멤버는 클래스의 모든 개체가 공유하는 개별 변수이므로 클래스 선언 외부에서 정의 및 초기화되어야 합니다.  클래스 및 클래스 멤버에 대한 자세한 내용은 [클래스](../cpp/classes-and-structs-cpp.md)를 참조하세요.  
  
4.  선언이 `class T;`과 같은 정의가 뒤따르지 않는 클래스 이름 선언입니다.  
  
5.  선언이 `typedef` 문입니다.  
  
 다음은 정의이기도 한 선언의 예제입니다.  
  
```  
// Declare and define int variables i and j.  
int i;  
int j = 10;  
  
// Declare enumeration suits.  
enum suits { Spades = 1, Clubs, Hearts, Diamonds };  
  
// Declare class CheckBox.  
class CheckBox : public Control  
{  
public:  
            Boolean IsChecked();  
    virtual int     ChangeState() = 0;  
};  
```  
  
 정의가 아닌 일부 선언은 다음과 같습니다.  
  
```  
  
extern int i;  
char *strchr( const char *Str, const char Target );  
```  
  
 선언자 바로 뒤, 이니셜라이저 앞\(선택 사항\)에서 이름이 선언된다고 간주합니다.  자세한 내용은 [선언 지점](../cpp/point-of-declaration-in-cpp.md)을 참조하세요.  
  
 선언은 *범위*에서 발생됩니다.  범위는 선언된 이름의 표시 및 정의된 개체\(있는 경우\)의 기간을 제어합니다.  범위 규칙이 선언에 사용되는 방법에 대한 자세한 내용은 [범위](../cpp/scope-visual-cpp.md)를 참조하세요.  
  
 개체 선언은 `extern`저장소 클래스 지정자에 설명된 [저장소 클래스 지정자가 포함된 경우를 제외하고는 정의이기도 합니다.](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c) 함수 선언도 프로토타입이 아니라면 정의입니다.  프로토타입은 정의 함수 본문이 없는 함수 헤더입니다.  개체 정의를 통해 해당 개체에 대해 저장소가 할당되고 적절한 초기화가 수행됩니다.  
  
## 정의  
 정의는 개체 또는 변수, 함수, 클래스 또는 열거자의 고유 사양입니다.  정의가 고유해야 하기 때문에 프로그램에는 지정된 프로그램 요소에 대한 정의가 하나만 포함될 수 있습니다.  선언과 정의 간에 다 대 일 대응이 있을 수 있습니다.  프로그램 요소가 선언되지만 정의되지는 않는 두 가지 경우가 있습니다.  
  
1.  함수가 선언되지만 함수 호출 또는 함수의 주소를 사용하는 식으로 참조되지 않습니다.  
  
2.  클래스가 정의가 알려질 필요가 없는 방식으로만 사용됩니다.  그러나 클래스는 선언되어야 합니다.  다음 코드에서는 이러한 경우를 보여 줍니다.  
  
    ```  
    // definitions.cpp  
    class WindowCounter;   // Forward declaration; no definition  
  
    class Window  
    {  
       // Definition of WindowCounter not required  
       static WindowCounter windowCounter;  
    };  
  
    int main()  
    {  
    }  
    ```  
  
## 참고 항목  
 [기본 개념](../cpp/basic-concepts-cpp.md)   
 [선언 지점](../cpp/point-of-declaration-in-cpp.md)