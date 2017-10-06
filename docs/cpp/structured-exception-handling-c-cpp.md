---
title: "구조적 예외 처리 (C/c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9098ac4914bdb9e054d4db27c0a5498c0f9d9ea8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)
Windows 및 Visual C++에서 SEH(구조적 예외 처리)를 지원하지만 포팅 가능하고 유연한 코드를 만들기 위해 ISO 표준 C++ 예외 처리를 사용하는 것이 좋습니다. 그러나 기존 코드 또는 특정 종류의 프로그램에서는 SEH를 계속 사용할 수 있습니다.  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
  
## <a name="grammar"></a>문법  
 *try 문을 제외 하 고* :  
  
 `__try`*복합 문*  
  
 `__except`( `expression` ) *복합 문*  
  
## <a name="remarks"></a>설명  
 SEH를 사용하면 실행이 예기치 않게 종료되는 경우 메모리 블록 및 파일과 같은 리소스가 올바른지 확인할 수 있습니다. `goto` 문을 사용하지 않는 간결한 구조의 코드나 반환 코드의 정교한 테스트를 사용하여 메모리 부족 등의 특정 문제를 처리할 수도 있습니다.  
  
 이 문서에서 참조된 try-except 및 try-finally 문은 C 언어에 대한 Microsoft 확장입니다. 둘 다 응용 프로그램이 그렇지 않을 경우 실행을 종료하는 이벤트 후에 프로그램을 제어할 수 있도록 하여 SEH를 지원합니다. SEH는 C++ 소스 파일에서 작동하지만 C++용으로 특별히 설계된 것은 아닙니다. 사용 하 여 컴파일하는 c + + 프로그램에서 SEH를 사용 하는 경우는 [/EH](../build/reference/eh-exception-handling-model.md) 옵션-특정 한정자와 함께-로컬 개체에 대 한 소멸자가 호출 되지만 다른 실행 동작은 예상과 되지 않을 수 있습니다. 설명을 보려면 이 문서의 뒷부분에 있는 예제를 참조하세요. 대부분의 경우에서 SEH 대신 권장 ISO 표준을 사용 하는 [c + + 예외 처리](../cpp/try-throw-and-catch-statements-cpp.md), Visual c + +도 지원입니다. C++ 예외 처리를 사용하면 코드 포팅 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다.  
  
 SEH를 사용하는 C 모듈이 있는 경우 C++ 예외 처리를 사용하는 C++ 모듈과 혼합할 수 있습니다. 자세한 내용은 참조 [예외 처리 차이점](../cpp/exception-handling-differences.md)합니다.  
  
 SEH 메커니즘에는 다음 두 가지가 있습니다.  
  
-   [예외 처리기](../cpp/writing-an-exception-handler.md)에 응답 하거나 예외를 해제할 수입니다.  
  
-   [종료 처리기](../cpp/writing-a-termination-handler.md), 예외 코드 블록에서 종료 하면 때 호출 됩니다.  
  
 이러한 두 종류의 처리기는 별개이지만 "스택 해제"라는 프로세스를 통해 긴밀하게 연결됩니다. 예외가 발생하면 Windows가 현재 활성 상태인 가장 최근에 설치된 예외 처리기를 찾습니다. 처리기는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.  
  
-   예외를 인식하지 못하고 다른 처리기에 제어를 전달합니다.  
  
-   예외를 인식하지만 해제합니다.  
  
-   예외를 인식하고 처리합니다.  
  
 예외가 발생할 때 실행 중이던 함수에 예외를 인식하는 예외 처리기가 없을 수 있습니다. 스택의 훨씬 상위 함수에 있는 경우도 있습니다. 현재 실행 중인 함수 및 스택 프레임의 다른 모든 함수가 종료됩니다. 이 과정에서 스택이 "해제"됩니다. 즉, `static`이 아닌 경우 종료된 함수의 지역 변수가 스택에서 지워집니다.  
  
 스택을 해제할 때 운영 체제는 각 함수에 대해 작성된 종료 처리기를 모두 호출합니다. 종료 처리기를 사용하면 그렇지 않을 경우 비정상적인 종료 때문에 열려 있을 리소스를 정리할 수 있습니다. 중요한 섹션을 입력한 경우 종료 처리기를 끝낼 수 있습니다. 프로그램이 종료되는 경우 임시 파일 닫기 및 제거와 같은 기타 관리 작업을 수행할 수 있습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [예외 처리기 작성](../cpp/writing-an-exception-handler.md)  
  
-   [종료 처리기 작성](../cpp/writing-a-termination-handler.md)  
  
-   [C++에서 구조적 예외 처리 사용](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## <a name="example"></a>예제  
 앞서 설명한 것 처럼, 소멸자는 c + + 프로그램에서 SEH를 사용 하 고 사용 하 여 컴파일하는 경우 로컬 개체는 호출 된는 **/EH** 특정 한정자와 함께 옵션-예를 들어 **/EHsc** 및 **/EHa**. 그러나 C++ 예외도 사용하는 경우 실행 중의 동작은 예상과 다를 수 있습니다. 다음 예제에서는 이러한 동작의 차이를 보여 줍니다.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 사용 하는 경우 **/EHsc** 이 코드 아니라 로컬 테스트 컨트롤을 컴파일하는 데 `CPPEX` 은 실행 하지 않아도 정의 되어 있지는 `TestClass` 소멸자 및 출력은 다음과 같이:  
  
```Output  
Triggering SEH exception  
Executing SEH __except block  
```  
  
 사용 하는 경우 **/EHsc** 코드를 컴파일하려면 및 `CPPEX` 사용 하 여 정의 `/DCPPEX` (c + + 예외를 throw 않도록), `TestClass` 소멸자가 실행 되며 출력은 다음과 같습니다.  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 사용 하는 경우 **/EHa** 는 코드를 컴파일하는 `TestClass` 소멸자를 사용 하 여 예외가 throw 하는지 여부에 관계 없이 실행할 `std::throw` 를 트리거하여 예외를 SEH를 사용 하 여 (`CPPEX` 정의 여부). 출력은 다음과 같습니다.  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 자세한 내용은 [/EH(예외 처리 모델)](../build/reference/eh-exception-handling-model.md)를 참조하세요.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [\<exception>](../standard-library/exception.md)   
 [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [구조적된 예외 처리 (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)
