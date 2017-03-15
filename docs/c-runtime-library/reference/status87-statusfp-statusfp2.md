---
title: _status87, _statusfp, _statusfp2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
dev_langs:
- C++
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: a42b5d8811e108b727671921322423d186d73afd
ms.lasthandoff: 02/24/2017

---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2
부동 소수점 상태 단어를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `px86`  
 이 주소에는 x87 부동 소수점 단위의 상태 단어가 채워집니다.  
  
 `pSSE2`  
 이 주소에는 SSE2 부동 소수점 단위의 상태 단어가 채워집니다.  
  
## <a name="return-value"></a>반환 값  
 `_status87` 및 `_statusfp`의 경우 반환되는 값의 비트는 부동 소수점 상태를 나타냅니다. `_statusfp`에서 반환하는 비트의 정의는 FLOOAT.H 포함 파일을 참조하세요. 대부분의 수학 라이브러리 함수는 부동 소수점 상태 단어를 수정하는데, 이 경우 예기치 않은 결과가 발생합니다. 최적화를 수행하면 `_status87`, `_statusfp` 및 관련 함수 호출을 다시 정렬/결합하고 해당 함수에 대한 부동 소수점 연산을 제거할 수 있습니다. 부동 소수점 연산을 다시 정렬하는 최적화가 수행되지 않도록 하려면 [/Od (Disable (Debug))](../../build/reference/od-disable-debug.md) 컴파일러 옵션 또는 [fenv_access](../../preprocessor/fenv-access.md) pragma 지시문을 사용합니다. 부동 소수점 상태 단어의 알려진 상태 간에 수행되는 부동 소수점 연산의 수가 적어지면 `_clearfp` 및 `_statusfp`의 반환 값과 `_statusfp2`의 반환 매개 변수의 안정성이 높아집니다.  
  
## <a name="remarks"></a>설명  
 `_statusfp` 함수는 부동 소수점 상태 단어를 가져옵니다. 상태 단어는 부동 소수점 프로세서 상태와 부동 소수점 예외 처리기에서 검색한 기타 조건(예: 부동 소수점 스택 오버플로 및 언더플로)의 조합입니다. 상태 단어의 내용을 반환하기 전에 마스킹되지 않은 예외를 확인합니다. 즉, 호출자에게 보류 중인 예외를 알립니다. x86 플랫폼에서 `_statusfp`는 x87 및 SSE2 부동 소수점 상태의 조합을 반환합니다. x64 플랫폼에서 반환되는 상태는 SSE의 MXCSR 상태를 기준으로 합니다. ARM 플랫폼에서 `_statusfp`는 FPSCR 레지스터의 상태를 반환합니다.  
  
 `_statusfp`는 플랫폼 독립적이며 `_status87`의 이식 가능한 버전입니다. 인텔(x86) 플랫폼에서는 `_status87`과 동일하고 x64 및 ARM 플랫폼에 의해 지원됩니다. 부동 소수점 코드를 모든 아키텍처로 이식할 수 있도록 하려면 `_statusfp`를 사용합니다. x86 플랫폼만 대상으로 하는 경우 `_status87` 또는 `_statusfp`를 사용할 수 있습니다.  
  
 x87 a및 SSE2 부동 소수점 프로세서가 둘 다 포함되어 있는 Pentium IV 등의 칩에 `_statusfp2`를 사용하는 것이 좋습니다. `_statusfp2`의 경우에는 x87 또는 SSE2 부동 소수점 프로세서 둘 다에 대해 부동 소수점 상태 단어를 사용하여 주소를 채웁니다. x87 및 SSE2 부동 소수점 프로세서를 지원하는 칩에서는 `_statusfp` 또는 `_controlfp`를 사용하며 작업이 x87 또는 SSE2 부동 소수점 상태 단어를 참조할 수 있으므로 모호한 경우 EM_AMBIGUOUS가 1로 설정됩니다. `_statusfp2` 함수는 x86 플랫폼에서만 지원됩니다.  
  
 이러한 함수에 대 한 유용 하지 않은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임 (CLR)에 기본 부동 소수점 정밀도만 지원 하기 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
```Output  
Status = 0x00000000 - clear  
Status = 0x00000003 - inexact, underflow  
Status = 0x00080003 - inexact, underflow, denormal  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
