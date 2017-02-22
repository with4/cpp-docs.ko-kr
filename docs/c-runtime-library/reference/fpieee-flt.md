---
title: "_fpieee_flt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpieee_flt"
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
  - "fpieee_flt"
  - "_fpieee_flt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fpieee_flt 함수"
  - "예외 처리, 부동 소수점"
  - "부동 소수점 예외 처리"
  - "fpieee_flt 함수"
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _fpieee_flt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

IEEE 부동 소수점 예외에 대한 사용자 정의 트랩 처리기를 호출합니다.  
  
## 구문  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### 매개 변수  
 `excCode`  
 예외 코드입니다.  
  
 `excInfo`  
 Windows NT 예외 정보 구조에 대한 포인터입니다.  
  
 `handler`  
 사용자의 IEEE 트랩 처리기 루틴에 대한 포인터입니다.  
  
## 반환 값  
 `_fpieee_flt` 의 반환 값은  `handler` 의해 반환 되는 값입니다.  이와같이, IEEE 필터 루틴은 구조적된 예외 처리 \(SEH\) 메커니즘의 절을 제외하고 사용할 수 있습니다.  
  
## 설명  
 `_fpieee_flt`  함수는 IEEE 부동 소수점 예외에 대한 사용자 정의 트랩 처리기를 호출하고 모든 관련 정보를 제공합니다.  이 루틴은 필요할 때 직접 IEEE 예외 처리기를 호출 하는 SEH 메커니즘에서 예외 필터 역할도 합니다.  
  
 Fpieee.h에 정의 된  `_FPIEEE_RECORD`  구조는 IEEE 부동 소수점 예외에 대한 정보를 포함합니다.  이 구조는  `_fpieee_flt` 로 사용자 정의 트랩 처리기에 전달됩니다.  
  
|\_FPIEEE\_RECORD 필드|설명|  
|-------------------------|--------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|이러한 필드는 시간에 예외가 발생 시간의 부동 소수점 환경에 대한 정보를 포함합니다.|  
|`unsigned int Operation`|트랩을 발생시킨 작업의 형식을 나타냅니다.  해당 형식이 비교 \(`_FpCodeCompare`\)일 경우,  `Result.Value`  필드의 특수한  `_FPIEEE_COMPARE_RESULT`  값 \(Fpieee.h에 정의 됨\)중 하나를 제공할 수 있습니다.  변환 형식 \(`_FpCodeConvert`\)은 트랩이 부동 소수점 변환 작업을 하는동안 발생했음을 나타냅니다.   `Operand1`  및 `Result` 형식을 살펴보면 변환이 시도되는 유형을 결정할 수 있습니다.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|이러한 구조는 제안된 결과 및 피연산자의 유형과 값을 나타냅니다<br /><br /> `OperandValid` 응답 값이 유효한지 여부를 나타내는 플래그입니다.<br /><br /> `Format` 해당 값의 데이터 형식입니다.  형식은 해당 값에 유효하지 않더라도 반환될 수 있습니다.<br /><br /> `Value` 결과 또는 피연산자 데이터 값입니다.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|\_FPIEEE\_EXCEPTION\_FLAGS는 부동 소수점 예외의 형식 당 1 비트 필드를 포함합니다.<br /><br /> 이러한 필드와 [\_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md)에 제공된 예외를 마스크하는데 사용하는 인수간에 대응관계가 있습니다.<br /><br /> 각 비트의 정확한 의미는 컨텍스트에 따라 달라집니다.<br /><br /> `Cause` 각 설정 비트는 발생 된 예외를 나타냅니다.<br /><br /> `Enable` 각 설정 비트는 특정 예외가 현재 마스크되지 않은 것을 나타냅니다.<br /><br /> `Status` 각 설정 비트는 특정 예외가 현재 보류된 것들을 나타냅니다.   `_controlfp` 에 의해 마스크 되었기 때문에 발생하지 못한 예외를 포함합니다.|  
  
 사용할 수 없는 보류 예외는 그것들을 사용할 떄 나타납니다.  예외 필터로  `_fpieee_flt` 를 사용하는 경우, 정의되지 않은 동작이 발생할 수 있습니다.  부동 소수점 예외를 사용 하도록 설정하기 전에, 항상  [\_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)를 호출합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fpieee_flt`|\<fpieee.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fpieee.c  
// This program demonstrates the implementation of  
// a user-defined floating-point exception handler using the  
// _fpieee_flt function.  
  
#include <fpieee.h>  
#include <excpt.h>  
#include <float.h>  
#include <stddef.h>  
  
int fpieee_handler( _FPIEEE_RECORD * );  
  
int fpieee_handler( _FPIEEE_RECORD *pieee )  
{  
   // user-defined ieee trap handler routine:  
   // there is one handler for all   
   // IEEE exceptions  
  
   // Assume the user wants all invalid   
   // operations to return 0.  
  
   if ((pieee->Cause.InvalidOperation) &&   
       (pieee->Result.Format == _FpFormatFp32))   
   {  
        pieee->Result.Value.Fp32Value = 0.0F;  
  
        return EXCEPTION_CONTINUE_EXECUTION;  
   }  
   else  
      return EXCEPTION_EXECUTE_HANDLER;  
}  
  
#define _EXC_MASK    \  
    _EM_UNDERFLOW  + \  
    _EM_OVERFLOW   + \  
    _EM_ZERODIVIDE + \  
    _EM_INEXACT  
  
int main( void )  
{  
   // ...  
  
   __try {  
      // unmask invalid operation exception  
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);   
  
      // code that may generate   
      // fp exceptions goes here  
   }  
   __except ( _fpieee_flt( GetExceptionCode(),  
                GetExceptionInformation(),  
                fpieee_handler ) ){  
  
      // code that gets control   
  
      // if fpieee_handler returns  
      // EXCEPTION_EXECUTE_HANDLER goes here  
  
   }  
  
   // ...  
}  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md)