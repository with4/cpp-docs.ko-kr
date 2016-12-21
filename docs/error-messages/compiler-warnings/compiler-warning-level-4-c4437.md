---
title: "컴파일러 경고(수준 4) C4437 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4437
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가상 기본 'class1'에서 'class2' 하려면 dynamic\_cast 수 \/vd2 된 컨텍스트에서 컴파일 실패 하거나 적용 'class2' \#pragma vtordisp\(2\) 사용하여 정의합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 컴파일러에서 `dynamic_cast` 작업을 발견하면서 다음과 같은 특징이 있습니다.  
  
-   기본 클래스 포인터에서 파생된 클래스 포인터 캐스트입니다.  
  
-   파생 클래스는 기본 클래스를 가상으로 상속합니다.  
  
-   파생된 클래스에 `vtordisp` 필드가 없습니다.  
  
-   캐스팅 생성자 또는 소멸자가 파생된 클래스의 없거나 일부 클래스의 추가 파생된 클래스 \(그렇지 않으면 컴파일러 경고 발생 합니다 C4436\)에서 상속 합니다.  
  
 경고는 `dynamic_cast` 이 부분적으로 생성 된 개체에서 작동 하는 경우 제대로 작동 하지 않을 수 있습니다.  이 경우 바깥쪽 함수 생성자 나 경고에 지정 된 파생된 클래스를 상속 하는 클래스의 소멸자가 호출 될 때 발생 합니다.  경고에 지정 된 파생된 클래스는 더 이상 파생 하는 경우, 또는 바깥쪽 함수는 개체 생성 또는 소멸 호출 되지 않습니다,이 경고를 무시할 수 있습니다.  
  
## 예제  
 다음 샘플은 C4436를 생성 하 고 누락 된에서 발생 하는 코드 생성 문제를 보여 줍니다. `vtordisp` 필드입니다.  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [컴파일러 경고\(수준 1\) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)