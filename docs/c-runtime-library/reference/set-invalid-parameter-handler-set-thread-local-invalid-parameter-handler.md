---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
dev_langs: C++
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 336a2f362ac9a67cb8bb176948fbb7b5c83329a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setinvalidparameterhandler-setthreadlocalinvalidparameterhandler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
CRT가 잘못된 인수를 발견할 때 호출할 함수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `pNew`  
 새로운 잘못된 매개 변수 처리기에 대한 함수 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 호출 이전의 잘못된 매개 변수 처리기에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 많은 C 런타임 함수가 자신에게 전달되는 인수의 유효성을 확인합니다. 잘못된 인수가 전달될 경우 이 함수는 `errno` 오류 번호를 설정하거나 오류 코드를 반환할 수 있습니다. 이 경우 잘못된 매개 변수 처리기도 호출됩니다. C 런타임은 프로그램을 종료하고 런타임 오류 메시지를 표시하는 기본 전역 잘못된 매개 변수 처리기를 제공합니다. `_set_invalid_parameter_handler`를 사용하면 고유한 함수를 전역 잘못된 매개 변수 처리기로 설정할 수 있습니다. 또한 C 런타임은 스레드 로컬 잘못된 매개 변수 처리기도 지원합니다. 스레드 로컬 매개 변수 처리기는 `_set_thread_local_invalid_parameter_handler`를 사용하여 스레드에서 설정됩니다. 스레드에서 호출된 C 런타임 함수는 전역 처리기가 아닌 이 처리기를 사용합니다. 한 번에 하나의 함수만 전역 잘못된 인수 처리기로 지정할 수 있습니다. 스레드당 하나의 함수만 스레드 로컬 잘못된 인수 처리기로 지정할 수 있지만, 각 스레드의 스레드 로컬 처리기는 서로 다를 수 있습니다. 따라서 다른 스레드의 동작에 영향을 주지 않고 코드의 특정 부분에서 사용되는 처리기를 변경할 수 있습니다.  
  
 런타임이 잘못된 매개 변수 함수를 호출할 때 이는 일반적으로 복구할 수 없는 오류가 발생했음을 의미합니다. 직접 제공하는 잘못된 매개 변수 처리기 함수는 저장할 수 있는 모든 데이터를 저장한 다음 중단되어야 하며, 오류를 확실히 복구할 수 있지 않는 한 컨트롤을 main 함수로 반환하면 안 됩니다.  
  
 잘못된 매개 변수 처리기 함수에는 다음과 같은 프로토타입이 있어야 합니다.  
  
```  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 `expression` 인수는 오류를 발생시킨 인수 식의 와이드 문자열 표현입니다. `function` 인수는 잘못된 인수를 받은 CRT 함수의 이름입니다. `file` 인수는 함수가 포함된 CRT 소스 파일의 이름입니다. `line` 인수는 해당 파일의 줄 번호입니다. 마지막 인수는 예약되어 있습니다. CRT 라이브러리의 디버그 버전이 사용되지 않는 한 모든 매개 변수에 `NULL` 값이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \<stdlib.h><br /><br /> C++: \<cstdlib> 또는 \<stdlib.h>|  
  
 `_set_invalid_parameter_handler` 및 `_set_thread_local_invalid_parameter_handler` 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는 잘못된 매개 변수 오류 처리기를 사용하여 잘못된 매개 변수를 받은 함수와 CRT 소스의 파일 및 줄을 출력합니다. 디버그 CRT 라이브러리가 사용되면 잘못된 매개 변수 오류도 어설션을 생성하지만 이 예제에서는 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)를 통해 사용되지 않도록 설정되었습니다.  
  
```C  
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
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32  
Expression: format != nullptr  
```  
  
## <a name="see-also"></a>참고 항목  
 [_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [보안이 강화된 CRT 함수 버전](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)