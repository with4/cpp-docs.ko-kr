---
title: "구조적 예외 처리 (C/C++) | Microsoft Docs"
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
  - "C++ 예외 처리, 예외 처리기"
  - "C++ 예외 처리, 종료 처리기"
  - "구조적 예외 처리"
  - "종료 처리기, C++에서의 예외 처리"
  - "try-catch 키워드[C++], 예외 처리기"
  - "try-catch 키워드[C++], 종료 처리기"
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 구조적 예외 처리 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 및 Visual C\+\+에서 SEH\(구조적 예외 처리\)를 지원하지만 포팅 가능하고 유연한 코드를 만들기 위해 ISO 표준 C\+\+ 예외 처리를 사용하는 것이 좋습니다.  그러나 기존 코드 또는 특정 종류의 프로그램에서는 SEH를 계속 사용할 수 있습니다.  
  
## Microsoft 전용  
  
## 문법  
 *try\-except\-statement* :  
  
 `__try` *compound\-statement*  
  
 `__except` \( `expression` \) *compound\-statement*  
  
## 설명  
 SEH를 사용하면 실행이 예기치 않게 종료되는 경우 메모리 블록 및 파일과 같은 리소스가 올바른지 확인할 수 있습니다.  `goto` 문을 사용하지 않는 간결한 구조의 코드나 반환 코드의 정교한 테스트를 사용하여 메모리 부족 등의 특정 문제를 처리할 수도 있습니다.  
  
 이 문서에서 참조된 try\-except 및 try\-finally 문은 C 언어에 대한 Microsoft 확장입니다.  둘 다 응용 프로그램이 그렇지 않을 경우 실행을 종료하는 이벤트 후에 프로그램을 제어할 수 있도록 하여 SEH를 지원합니다.  SEH는 C\+\+ 소스 파일에서 작동하지만 C\+\+용으로 특별히 설계된 것은 아닙니다.  특정 한정자와 함께 [\/EH](../build/reference/eh-exception-handling-model.md) 옵션을 사용하여 컴파일한 C\+\+ 프로그램에서 SEH를 사용하는 경우 로컬 개체에 대한 소멸자가 호출되지만 다른 실행 동작은 예상과 다를 수도 있습니다.  설명을 보려면 이 문서의 뒷부분에 있는 예제를 참조하세요. 대부분의 경우 SEH 대신 Visual C\+\+에서도 지원하는 ISO 표준 [C\+\+ 예외 처리](../cpp/try-throw-and-catch-statements-cpp.md)를 사용하는 것이 좋습니다.  C\+\+ 예외 처리를 사용하면 코드 포팅 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다.  
  
 SEH를 사용하는 C 모듈이 있는 경우 C\+\+ 예외 처리를 사용하는 C\+\+ 모듈과 혼합할 수 있습니다.  자세한 내용은 [예외 처리 차이점](../cpp/exception-handling-differences.md)을 참조하세요.  
  
 SEH 메커니즘에는 다음 두 가지가 있습니다.  
  
-   [예외 처리기](../cpp/writing-an-exception-handler.md) \- 예외에 응답하거나 해제할 수 있습니다.  
  
-   [종료 처리기](../cpp/writing-a-termination-handler.md) \- 예외로 인해 코드 블록이 종료될 때 호출됩니다.  
  
 이러한 두 종류의 처리기는 별개이지만 "스택 해제"라는 프로세스를 통해 긴밀하게 연결됩니다. 예외가 발생하면 Windows가 현재 활성 상태인 가장 최근에 설치된 예외 처리기를 찾습니다.  처리기는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.  
  
-   예외를 인식하지 못하고 다른 처리기에 제어를 전달합니다.  
  
-   예외를 인식하지만 해제합니다.  
  
-   예외를 인식하고 처리합니다.  
  
 예외가 발생할 때 실행 중이던 함수에 예외를 인식하는 예외 처리기가 없을 수 있습니다.  스택의 훨씬 상위 함수에 있는 경우도 있습니다.  현재 실행 중인 함수 및 스택 프레임의 다른 모든 함수가 종료됩니다.  이 과정에서 스택이 "해제"됩니다. 즉, `static`이 아닌 경우 종료된 함수의 지역 변수가 스택에서 지워집니다.  
  
 스택을 해제할 때 운영 체제는 각 함수에 대해 작성된 종료 처리기를 모두 호출합니다.  종료 처리기를 사용하면 그렇지 않을 경우 비정상적인 종료 때문에 열려 있을 리소스를 정리할 수 있습니다.  중요한 섹션을 입력한 경우 종료 처리기를 끝낼 수 있습니다.  프로그램이 종료되는 경우 임시 파일 닫기 및 제거와 같은 기타 관리 작업을 수행할 수 있습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [예외 처리기 작성](../cpp/writing-an-exception-handler.md)  
  
-   [종료 처리기 작성](../cpp/writing-a-termination-handler.md)  
  
-   [C\+\+에서 구조적 예외 처리 사용](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## 예제  
 앞서 설명한 것처럼, C\+\+ 프로그램에서 SEH를 사용하고 특정 한정자와 함께 **\/EH** 옵션을 사용하여 컴파일하는 경우\(예: **\/EHsc** 및 **\/EHa**\) 로컬 개체에 대한 소멸자가 호출됩니다.  그러나 C\+\+ 예외도 사용하는 경우 실행 중의 동작은 예상과 다를 수 있습니다.  다음 예제에서는 이러한 동작의 차이를 보여 줍니다.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 **\/EHsc**를 사용하여 이 코드를 컴파일하지만 로컬 테스트 컨트롤 `CPPEX`가 정의되지 않은 경우 `TestClass` 소멸자가 실행되지 않으며 출력은 다음과 같습니다.  
  
  **SEH 예외 트리거**  
**SEH \_\_except 블록 실행** **\/EHsc**를 사용하여 코드를 컴파일하고, C\+\+ 예외가 발생하도록 `CPPEX`가 `/DCPPEX`를 사용하여 정의된 경우 `TestClass` 소멸자가 실행되며 출력은 다음과 같습니다.  
  
  **C\+\+ 예외 발생**  
**TestClass 소멸  SEH \_\_except 블록 실행**  **\/EHa**를 사용하여 코드를 컴파일하는 경우 `std::throw`를 사용하여 예외를 발생했는지 또는 SEH로 예외를 트리거하여 예외를 발생했는지에 관계없이\(`CPPEX` 정의 여부\) `TestClass` 소멸자가 실행됩니다.  출력은 다음과 같습니다.  
  
  **C\+\+ 예외 발생**  
**TestClass 소멸  SEH \_\_except 블록 실행**  자세한 내용은 [\/EH\(예외 처리 모델\)](../build/reference/eh-exception-handling-model.md)를 참조하세요.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [\<exception\>](../standard-library/exception.md)   
 [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [구조적 예외 처리\(Windows\) \(영문\)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)