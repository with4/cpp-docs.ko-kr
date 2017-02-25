---
title: "try-except 문 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_abnormal_termination_cpp"
  - "_exception_code_cpp"
  - "EXCEPTION_CONTINUE_SEARCH"
  - "_exception_info"
  - "__except"
  - "EXCEPTION_CONTINUE_EXECUTION"
  - "_exception_code"
  - "__except_cpp"
  - "_exception_info_cpp"
  - "EXCEPTION_EXECUTE_HANDLER"
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try 키워드[C++]"
  - "_abnormal_termination 키워드[C++]"
  - "_exception_code 키워드[C++]"
  - "_exception_info 키워드[C++]"
  - "EXCEPTION_CONTINUE_EXECUTION 매크로"
  - "EXCEPTION_CONTINUE_SEARCH 매크로"
  - "EXCEPTION_EXECUTE_HANDLER 매크로"
  - "GetExceptionCode 함수"
  - "try-catch 키워드[C++], try-except 키워드[C++]"
  - "try-except 키워드[C++]"
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# try-except 문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 구문에서는 try\-except 문에 대해 설명합니다.  
  
## 구문  
  
```  
  
      __try   
{  
   // guarded code  
}  
__except ( expression )  
{  
   // exception handler code  
}  
```  
  
## 설명  
 **try\-except** 문은 정상적으로 프로그램 실행을 종료시키는 이벤트가 발생할 때, 대상 응용 프로그램이 제어할 수 있도록 하는 C와 C\+\+언어의 Microsoft 확장입니다.  이러한 이벤트를 예외라고 하고 예외를 처리하는 메커니즘은 구조적 예외 처리라고 합니다.  
  
 관련 내용은 [try\-finally 문](../cpp/try-finally-statement.md)을 참조하십시오.  
  
 예외는 하드웨어 기반 또는 소프트웨어 기반일 수 있습니다.  응용 프로그램을 하드웨어 또는 소프트웨어 예외로부터 완전히 복구할 수 없더라도 구조적 예외 처리를 통해 오류 정보를 표시하고 응용 프로그램의 내부 상태를 트래핑하여 문제를 진단하는 데 도움이 되도록 합니다.  이것은 쉽게 재현할 수 없는 간헐적인 문제에 특히 유용합니다.  
  
> [!NOTE]
>  구조적 예외 처리는 Win32에서 C 및 C\+\+ 소스 파일에 대해 작동하지만  특별히 C\+\+용으로 설계되지는 않았습니다.  C\+\+ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다.  또한 C\+\+ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다.  C\+\+ 프로그램의 경우 C\+\+ 예외 처리 메커니즘을 사용하는 것이 좋습니다\([try, catch, throw](../cpp/try-throw-and-catch-statements-cpp.md) 문\).  
  
 `__try` 절 뒤에 오는 복합 문은 본문 또는 보호된 섹션입니다.  `__except` 절 뒤에 오는 복합 문은 예외 처리기입니다.  처리기는 보호된 섹션 본문을 실행하는 동안 예외가 발생하는 경우 수행할 일련의 작업을 지정합니다.  다음과 같이 실행됩니다.  
  
1.  보호된 섹션이 실행됩니다.  
  
2.  보호된 섹션을 실행하는 동안 예외가 발생하지 않는 경우 `__except` 절 다음의 문에서 실행이 계속됩니다.  
  
3.  보호된 섹션의 실행 중 또는 보호된 섹션이 호출하는 임의의 루틴에서 예외가 발생할 경우 `__except`식\(필터 식이라고 함\)이 계산되고 그 값이 예외 처리 방식을 결정합니다.  다음과 같은 세 가지 값이 있습니다.  
  
     **EXCEPTION\_CONTINUE\_EXECUTION \(–1\)** 예외를 무시합니다.  예외가 발생한 지점에서 계속 실행합니다.  
  
     **EXCEPTION\_CONTINUE\_SEARCH \(0\)** 예외를 인식하지 못합니다.  **try\-except** 문을 포함하는 처리기를 먼저 검색한 후, 그 다음으로 우선 순위가 높은 처리기를 검색하는 순으로 처리기 스택을 계속 검색합니다.  
  
     **EXCEPTION\_EXECUTE\_HANDLER \(1\)** 예외를 인식합니다.  `__except` 복합 문을 실행하여 예외 처리기로 제어를 전달하고, `__except` 블록 이후 실행을 계속합니다.  
  
 \_\_**except** 식은 C 식으로 계산되므로 단일 값, 조건식 연산자 또는 쉼표 연산자로 제한됩니다.  더 광범위한 처리가 필요한 경우 식은 위에 나열된 세 값 중 하나를 반환하는 루틴을 호출할 수 있습니다.  
  
 각 응용 프로그램에는 자체 예외 처리기를 사용할 수 있습니다.  
  
 자체 예외 처리기는 `__try` 문으로 이동할 수는 없지만 해당 문 밖으로 이동하는 것은 가능합니다.  **try\-except** 문을 실행하는 도중에 프로세스를 종료할 경우 예외 처리기가 호출되지 않습니다.  
  
 자세한 내용은 기술 자료 문서, "Q315937: 방법: Visual C\+\+ 응용 프로그램에서 스택 오버플로 감지"를 참조하십시오.  
  
## \_\_leave 키워드  
 `__leave` 키워드는 `try-except` 문의 보호된 섹션 내에서만 유효하며, 보호된 섹션의 끝으로 이동하도록 합니다.  실행은 예외 처리기 뒤에 나오는 첫 번째 문에서 계속 됩니다.  
  
 또한 `goto` 문은 보호된 섹션에서 외부로 이동할 수 있으며 스택 해제가 발생하지 않기 때문에 `try-finally` 문에서 실행될 때 성능이 저하되지 않습니다.  하지만 보호된 섹션이 크거나 복잡할 경우 프로그래밍 실수를 할 가능성이 줄어들기 때문에 `goto` 문보다는 `__leave` 키워드를 사용하는 것이 좋습니다.  
  
### 구조적 예외 처리 내장 함수  
 구조화된 예외 처리는 **try\-except** 문과 함께 사용할 수 있는 2개의 내장 함수인 **GetExceptionCode**와 **GetExceptionInformation**을 제공합니다.  
  
 **GetExceptionCode**는 예외 코드\(32비트 정수\)를 반환합니다.  
  
 **GetExceptionInformation** 내장 함수는 예외에 대한 추가 정보가 포함되어 있는 구조체에 포인터를 반환합니다.  이 포인터를 통하여, 하드웨어 예외 발생 시의 컴퓨터 상태에 액세스할 수 있습니다.  구조체는 다음과 같습니다.  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 포인터 형식, \_**EXCEPTION\_RECORD** 및 \_**CONTEXT**는 EXCPT.H include 파일에서 정의됩니다.  
  
 예외 처리기 내에서 **GetExceptionCode**를 사용할 수 있습니다.  하지만 **GetExceptionInformation**은 예외 필터 식 내에서만 사용할 수 있습니다.  해당 내장 함수가 가리키는 정보는 일반적으로 스택에 있으며, 예외 처리기로 제어가 전달되면 더 이상 사용할 수 없습니다.  
  
 **AbnormalTermination** 내장 함수는 종료 처리기 내에서 사용할 수 있습니다.  `try-finally` 문의 본문이 순차적으로 종료되면 0을 반환합니다.  다른 모든 경우에는 1이 반환됩니다.  
  
 EXCPT.H는 다음과 같은 내장 함수에 대해 일부 대체 이름을 정의합니다.  
  
 **GetExceptionCode**는 \_exception\_code에 해당합니다.  
  
 **GetExceptionInformation**은 \_exception\_info에 해당합니다.  
  
 **AbnormalTermination**은 \_abnormal\_termination에 해당합니다.  
  
## 예제  
 `// exceptions_try_except_Statement.cpp`  
  
 `// Example of try-except and try-finally statements`  
  
 `#include <stdio.h>`  
  
 `#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION`  
  
 `#include <excpt.h>`  
  
 `int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep) {`  
  
 `puts("in filter.");`  
  
 `if (code == EXCEPTION_ACCESS_VIOLATION) {`  
  
 `puts("caught AV as expected.");`  
  
 `return EXCEPTION_EXECUTE_HANDLER;`  
  
 `}`  
  
 `else {`  
  
 `puts("didn't catch AV, unexpected.");`  
  
 `return EXCEPTION_CONTINUE_SEARCH;`  
  
 `};`  
  
 `}`  
  
 `int main()`  
  
 `{`  
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## Output  
  
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
  
## 참고 항목  
 [예외 처리기 작성](../cpp/writing-an-exception-handler.md)   
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)