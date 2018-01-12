---
title: "시도-문을 제외 하 고 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs: C++
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 240b8ad1b0cfd9c8b85b58c8d2309fb97f961573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="try-except-statement"></a>try-except 문

**Microsoft 전용**  
**시도-제외 하 고** 구조적 예외 처리를 지 원하는 c + + 언어 및 문은 C에는 Microsoft 확장입니다.  

## <a name="syntax"></a>구문  
  
> **__try**   
> {  
>    보호 된 코드  
> }  
> **__except** ( *식* )  
> {  
>    예외 처리기 코드  
> }  

## <a name="remarks"></a>설명

**시도-제외 하 고** 문은 C에 대 한 Microsoft 확장 이며 대상 응용 프로그램을 얻을 수 있도록 하는 c + + 언어 정상적으로 프로그램 실행을 종료 시키는 이벤트가 발생할 때 제어 합니다. 이러한 이벤트 라고 *예외*, 고 예외를 처리 하는 메커니즘은 라고 *구조적 예외 처리* (SEH).

관련된 정보에 대 한 참조는 [try-finally 문](../cpp/try-finally-statement.md)합니다.

예외는 하드웨어 기반 또는 소프트웨어 기반일 수 있습니다. 응용 프로그램을 하드웨어 또는 소프트웨어 예외로부터 완전히 복구할 수 없더라도 구조적 예외 처리를 통해 오류 정보를 표시하고 응용 프로그램의 내부 상태를 트래핑하여 문제를 진단하는 데 도움이 되도록 합니다. 이것은 쉽게 재현할 수 없는 간헐적인 문제에 특히 유용합니다.

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. C + + 프로그램에 대 한 것이 좋습니다 c + + 예외 처리 메커니즘을 사용 하는 ([try, catch 및 throw](../cpp/try-throw-and-catch-statements-cpp.md) 문).

`__try` 절 뒤에 오는 복합 문은 본문 또는 보호된 섹션입니다. `__except` 절 뒤에 오는 복합 문은 예외 처리기입니다. 처리기는 보호된 섹션 본문을 실행하는 동안 예외가 발생하는 경우 수행할 일련의 작업을 지정합니다. 다음과 같이 실행됩니다.

1. 보호된 섹션이 실행됩니다.

2. 보호된 섹션을 실행하는 동안 예외가 발생하지 않는 경우 `__except` 절 다음의 문에서 실행이 계속됩니다.  

3. 보호 된 섹션의 실행 하는 동안 예외가 발생 하거나 임의의 루틴에서 보호 된 섹션을 호출 하는 `__except` *식* (라는 *필터* 식) 평가 값 예외를 처리 하는 방법을 결정 합니다. 다음과 같은 세 가지 값이 있습니다.

   **EXCEPTION_CONTINUE_EXECUTION (-1)** 예외를 무시 합니다. 예외가 발생한 지점에서 계속 실행합니다.

   **EXCEPTION_CONTINUE_SEARCH (0)** 예외가 인식 되지 않습니다. **try-except** 문을 포함하는 처리기를 먼저 검색한 후, 그 다음으로 우선 순위가 높은 처리기를 검색하는 순으로 처리기 스택을 계속 검색합니다.

   **EXCEPTION_EXECUTE_HANDLER (1)** 예외를 인식 합니다. `__except` 복합 문을 실행하여 예외 처리기로 제어를 전달하고, `__except` 블록 이후 실행을 계속합니다.

`__except` 식은 C 식으로 계산되므로 단일 값, 조건식 연산자 또는 쉼표 연산자로 제한됩니다. 더 광범위한 처리가 필요한 경우 식은 위에 나열된 세 값 중 하나를 반환하는 루틴을 호출할 수 있습니다.

각 응용 프로그램에는 자체 예외 처리기를 사용할 수 있습니다.

자체 예외 처리기는 `__try` 문으로 이동할 수는 없지만 해당 문 밖으로 이동하는 것은 가능합니다. 프로세스 실행 중에 종료 되는 경우 예외 처리기가 호출 되지는 **시도-제외 하 고** 문.  
  
자세한 내용은 기술 자료 문서, "Q315937: 방법: Visual C++ 응용 프로그램에서 스택 오버플로 감지"를 참조하십시오.  
  
## <a name="the-leave-keyword"></a>__leave 키워드

`__leave` 키워드는 보호 된 섹션 내 에서만 사용할 수는 **시도-제외 하 고** 문과 효과 보호 된 섹션의 끝으로 이동 하는 것입니다. 실행은 예외 처리기 뒤에 나오는 첫 번째 문에서 계속 됩니다.

A `goto` 문은 보호 된 섹션에서 외부로 이동할 수도 수 및와 마찬가지로 성능을 저하 되지 않습니다는 **try-finally** 문은 스택 해제 발생 하지 않으므로 합니다. 하지만 보호된 섹션이 크거나 복잡할 경우 프로그래밍 실수를 할 가능성이 줄어들기 때문에 `__leave` 문보다는 `goto` 키워드를 사용하는 것이 좋습니다.

### <a name="structured-exception-handling-intrinsic-functions"></a>구조적 예외 처리 내장 함수

구조적된 예외 처리 사용 시 사용할 수 있는 두 가지 내장 함수를 제공 합니다.는 **시도-제외 하 고** 문을: `GetExceptionCode` 및 `GetExceptionInformation`합니다.

`GetExceptionCode`예외의 코드 (32 비트 정수)를 반환합니다.

내장 함수 `GetExceptionInformation` 예외에 대 한 추가 정보가 포함 된 구조에 대 한 포인터를 반환 합니다. 이 포인터를 통하여, 하드웨어 예외 발생 시의 컴퓨터 상태에 액세스할 수 있습니다. 구조체는 다음과 같습니다.

```cpp  
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS; 
```  

포인터 형식 `PEXCEPTION_RECORD` 및 `PCONTEXT` WINNT 포함 파일에 정의 됩니다. H, 및 `_EXCEPTION_RECORD` 및 `_CONTEXT` EXCPT 포함 파일에 정의 됩니다. H

사용할 수 있습니다 `GetExceptionCode` 예외 처리기 내에서. 사용할 수 있습니다 `GetExceptionInformation` 예외 필터 식 내 에서만. 해당 내장 함수가 가리키는 정보는 일반적으로 스택에 있으며, 예외 처리기로 제어가 전달되면 더 이상 사용할 수 없습니다.

내장 함수 `AbnormalTermination` 종료 처리기 내에서 사용할 수 있습니다. 경우에 0을 반환의 본문은 **try-finally** 문은 순차적으로 종료 합니다. 다른 모든 경우에는 1이 반환됩니다.

EXCPT.H는 다음과 같은 내장 함수에 대해 일부 대체 이름을 정의합니다.

`GetExceptionCode`가 같음`_exception_code`

 `GetExceptionInformation`가 같음`_exception_info`

 `AbnormalTermination`가 같음`_abnormal_termination`
  
## <a name="example"></a>예

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```
  
## <a name="output"></a>출력  
  
```  
hello  
in try  
in try  
in filter.  
caught AV as expected.  
in finally. termination:  
        abnormal  
in except  
world  
```  

**Microsoft 전용 종료**  

## <a name="see-also"></a>참고 항목

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)   
[구조적된 예외 처리 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md)   
[키워드](../cpp/keywords-cpp.md)
