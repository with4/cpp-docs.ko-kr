---
title: "/Zc:implicitNoexcept(암시적 예외 지정자) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:implicitNoexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc:implicitNoexcept"
  - "Zc:implicitNoexcept"
  - "-Zc:implicitNoexcept"
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:implicitNoexcept(암시적 예외 지정자)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:implicitNoexcept** 옵션을 지정하면 컴파일러는 컴파일러가 정의한 특수 멤버 함수 및 사용자가 정의한 소멸자 및 비할당자에 암시적 [noexcept](../../cpp/noexcept-cpp.md) 예외 지정자를 추가합니다.  기본적으로 **\/Zc:implicitNoexcept**는 ISO C\+\+11 표준에 따라 사용하도록 설정됩니다.  이 옵션을 해제하면 사용자가 정의한 소멸자 및 비할당자와 컴파일러가 정의한 특수 멤버 함수에 암시적 `noexcept`를 사용하지 않습니다.  
  
## 구문  
  
```vb  
/Zc:implicitNoexcept[-]  
```  
  
#### 매개 변수  
  
## 설명  
 기본적으로, **\/Zc:implicitNoexcept**가 지정된 경우 컴파일러는 ISO C\+\+11 표준 15.4 항에 따라 암시적으로 선언되었거나 명시적으로 기본값 설정된 각 특수 멤버 함수\(기본 생성자, 복사 생성자, 이동 생성자, 소멸자, 복사 할당 연산자 또는 이동 할당 연산자\) 및 각 사용자 정의 소멸자 또는 비할당자 함수에 암시적으로 `noexcept` 예외 지정자를 추가합니다.  사용자 정의 비할당자에는 암시적 `noexcept(true)` 예외 지정자가 있습니다.  사용자 정의 소멸자의 경우 포함된 멤버 클래스 또는 기본 클래스에 `noexcept(true)`가 아닌 소멸자가 없는 한, 암시적 예외 지정자는 `noexcept(true)`입니다.  컴파일러에서 생성된 특수 멤버 함수의 경우 이 함수에 의해 직접 호출되는 함수는 실질적으로 `noexcept(false)`이며 암시적 예외 지정자는 `noexcept(false)`입니다.  그렇지 않은 경우 암시적 예외 지정자는 `noexcept(true)`입니다.  
  
 컴파일러는 명시적인 `noexcept` 또는 `throw` 지정자나 `__declspec(nothrow)` 특성을 사용하여 선언된 함수에 대해 암시적 예외 지정자를 생성하지 않습니다.  
  
 **\/Zc:implicitNoexcept\-**를 지정하여 이 옵션을 사용하지 않도록 설정하는 경우 컴파일러에서 암시적 예외 지정자가 생성되지 않습니다.  이 동작은 Visual Studio 2013과 같습니다. Visual Studio 2013에서는 예외 지정자가 없는 소멸자 및 비할당자에 `throw` 문이 있습니다.  기본적으로, 그리고 **\/Zc:implicitNoexcept**가 지정된 경우, 암시적 `noexcept(true)` 지정자가 있는 함수에서 런타임에 `throw` 문이 발견되면 즉시 `std::terminate`가 호출되며 예외 처리기의 정상적인 해제 동작이 보장되지 않습니다.  이 상황을 식별할 수 있도록 컴파일러는 [컴파일러 경고 \(수준 1\) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)을 생성합니다.  `throw`가 의도한 것이라면 **\/Zc:implicitNoexcept\-**를 사용하는 대신 명시적 `noexcept(false)` 지정자를 사용하도록 함수 선언을 변경하는 것이 좋습니다.  
  
 이 샘플에서는 **\/Zc:implicitNoexcept** 옵션을 설정하거나 사용하지 않도록 설정하는 경우 명시적 예외 지정자가 없는 사용자 정의 소멸자가 어떻게 동작하는지 보여 줍니다.  설정된 경우의 동작을 확인하려면 `cl /EHsc /W4 implicitNoexcept.cpp`를 사용하여 컴파일합니다.  사용하지 않도록 설정된 경우의 동작을 확인하려면 `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`를 사용하여 컴파일합니다.  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 기본 설정 **\/Zc:implicitNoexcept**를 사용하여 컴파일하면 샘플이 다음 출력을 생성합니다.  
  
  **~B 예외를 catch했습니다.**  
**예기치 않은 throw로 인해 std::terminate가 발생했습니다.**  
**종료하고 EXIT\_FAILURE를 반환합니다.** 설정 **\/Zc:implicitNoexcept\-**를 사용하여 컴파일하면 샘플이 다음 출력을 생성합니다.  
  
  **~B 예외를 catch했습니다.**  
**~D 예외를 catch했습니다.**  
**종료하고 EXIT\_SUCCESS를 반환합니다.** Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)을 참조하세요.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **\/Zc:implicitNoexcept** 또는 **\/Zc:implicitNoexcept\-**를 포함하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택합니다.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [예외 사양\(throw\)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../Topic/terminate%20\(%3Cexception%3E\).md)