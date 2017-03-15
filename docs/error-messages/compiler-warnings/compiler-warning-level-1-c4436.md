---
title: "컴파일러 경고(수준 1) C4436 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# 컴파일러 경고(수준 1) C4436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class2' 생성자 나 소멸자를 가상 기본 'class1'에서 dynamic\_cast \/vd2와 부분적으로 생성 된 개체 컴파일 실패 하거나 적용 'class2' \#pragma vtordisp\(2\) 사용 하 여 정의할 수 있습니다.  
  
 컴파일러에서  `dynamic_cast`  작업을 발견하면서 다음과 같은 특징이 있습니다.  
  
-   기본 클래스 포인터에서 파생된 클래스 포인터 캐스트입니다.  
  
-   파생 클래스는 기본 클래스를 가상으로 상속합니다.  
  
-   파생된 클래스에 `vtordisp` 필드가 없습니다.  
  
-   생성자 또는 소멸자가 파생된 클래스의 캐스팅 찾거나 일부 클래스의 추가 파생된 클래스에서 상속 합니다.  
  
 경고는 `dynamic_cast` 이 부분적으로 생성 된 개체에서 작동 하는 경우 제대로 작동 하지 않을 수 있습니다.  하는 몇 가지 더 파생 된 개체의 하위 개체에서 파생 된 생성자\/소멸자 작동 하는 경우 발생 합니다.  라는 경고에서 파생된 된 클래스는 더 이상 경우 파생에 경고를 무시할 수 있습니다.  
  
## 예제  
 다음 샘플은 C4436를 생성 하 고 누락된 것에서 발생 하는 코드 생성 문제를 보여 줍니다.  `vtordisp`  필드입니다.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## 참고 항목  
 [dynamic\_cast 연산자](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [컴파일러 경고\(수준 4\) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)