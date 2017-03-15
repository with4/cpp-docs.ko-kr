---
title: "_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_invalid_parameter_handler"
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid parameter 처리기"
  - "set_invalid_parameter_handler 함수"
  - "_set_invalid_parameter_handler 함수"
  - "_set_thread_local_invalid_parameter_handler 함수"
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT가 잘못된 인수를 발견할 때 호출할 함수를 설정합니다.  
  
## 구문  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### 매개 변수  
 \[in\] `pNew`  
 새로운 잘못된 매개 변수 처리기에 대한 함수 포인터입니다.  
  
## 반환 값  
 호출 이전의 잘못된 매개 변수 처리기에 대한 포인터입니다.  
  
## 설명  
 많은 C 런타임 함수에 전달 되는 인수의 유효성을 확인 합니다. 잘못된 인수가 전달될 경우 이 함수는 `errno` 오류 번호를 설정하거나 오류 코드를 반환할 수 있습니다. 이 경우 잘못된 매개 변수 처리기도 호출됩니다. C 런타임이 프로그램을 종료 하 고 런타임 오류 메시지를 표시 하는 기본 글로벌 잘못 된 매개 변수 처리기를 제공 합니다. 사용할 수는 `_set_invalid_parameter_handler` 글로벌 잘못 된 매개 변수 처리기로 사용자 고유의 함수를 설정할 수 있습니다. 또한 C 런타임 스레드 로컬 잘못 된 매개 변수 처리기를 지원합니다. 스레드 로컬 매개 변수 처리기를 사용 하 여 스레드에 설정 되어 있는지 `_set_thread_local_invalid_parameter_handler`, 스레드에서 호출 C 런타임 함수 대신 전역 처리기 해당 처리기를 사용 합니다. 한 번에 하나의 함수를 전역 잘못 된 인수 처리기로 지정할 수 있습니다. 스레드당 스레드 로컬 잘못 된 인수 처리기로 하나의 함수를 지정할 수 있지만 서로 다른 스레드에서 다른 스레드 로컬 처리기에 있을 수 있습니다. 이 통해 다른 스레드의 동작에 영향을 주지 않고 코드의 한 부분에 사용 되는 처리기를 변경할 수 있습니다.  
  
 런타임에 잘못 된 매개 변수 함수를 호출 하는 경우에 일반적으로 복구할 수 없는 오류가 발생 했음을 의미 합니다. 제공한 잘못 된 매개 변수 처리기 함수를 중단 하 고 수 데이터를 저장 해야 합니다. 오류를 확실히 복구할 수 있지 않는 한 컨트롤을 main 함수로 반환하면 안 됩니다.  
  
 잘못된 매개 변수 처리기 함수에는 다음과 같은 프로토타입이 있어야 합니다.  
  
```c  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 `expression` 인수는 오류를 발생 시킨 인수 식의 와이드 문자열 표현입니다.`function` 인수는 잘못 된 인수를 받은 CRT 함수의 이름입니다.`file` 인수는 함수를 포함 하는 CRT 소스 파일의 이름입니다.`line` 인수는 해당 파일의 줄 번호입니다. 마지막 인수는 예약되어 있습니다. CRT 라이브러리의 디버그 버전이 사용되지 않는 한 모든 매개 변수에 `NULL` 값이 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C \+ \+: \< d l i b \> 또는 \< stdlib.h \>|  
  
 `_set_invalid_parameter_handler` 및 `_set_thread_local_invalid_parameter_handler` 함수는 Microsoft 전용입니다. 호환성 정보를 참조 하십시오. [호환성](../../c-runtime-library/compatibility.md)합니다.  
  
## 예제  
 다음 예제에서는 잘못된 매개 변수 오류 처리기를 사용하여 잘못된 매개 변수를 받은 함수와 CRT 소스의 파일 및 줄을 출력합니다. 잘못 된 매개 변수 오류도 어설션을 사용 하 여이 예제에서 해제 되어 있는 CRT 디버그 라이브러리를 사용 하는 경우 발생 시켜야 [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)합니다.  
  
```c  
// crt_set_invalid_parameter_handler.c  
// compile with: /Zi /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
  
void myInvalidParameterHandler(const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter detected in function %s."  
            L" File: %s Line: %d\n", function, file, line);  
   wprintf(L"Expression: %s\n", expression);  
   abort();  
}  
  
int main( )  
{  
   char* formatString;  
  
   _invalid_parameter_handler oldHandler, newHandler;  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   // Call printf_s with invalid parameters.  
  
   formatString = NULL;  
   printf(formatString);  
}  
```  
  
```Output  
잘못 된 매개 변수를 함수 common_vfprintf에서 발견 했습니다. 파일: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp 줄: 32 식: 형식! nullptr =  
```  
  
## 참고 항목  
 [\_get\_invalid\_parameter\_handler, \_get\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [보안이 강화된 CRT 함수 버전](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)