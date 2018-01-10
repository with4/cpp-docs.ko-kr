---
title: "_controlfp_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _controlfp_s
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
- controlfp_s
- _controlfp_s
dev_langs: C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8c8f651e04a1d68cd27f8321d6a30250c0e6ce1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="controlfps"></a>_controlfp_s
부동 소수점 제어 단어를 가져와서 설정합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)의 이 버전에는 보안 향상 기능이 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `currentControl`  
 현재 제어 단어 비트 값입니다.  
  
 `newControl`  
 새 제어 단어 비트 값입니다.  
  
 `mask`  
 설정할 새 제어 단어 비트의 마스크입니다.  
  
## <a name="return-value"></a>반환 값  
 0(성공하는 경우) 또는 `errno` 값 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 `_controlfp_s` 함수는 플랫폼 독립적이며 `_control87`의 더 안전한 버전으로, `currentControl`에 저장되어 있는 주소로 부동 소수점 제어 단어를 가져오고 `newControl`을 사용하여 이를 설정합니다. 값의 비트는 부동 소수점 제어 상태를 나타냅니다. 부동 소수점 제어 상태를 사용하면 프로그램이 플랫폼에 따라 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. `_controlfp_s`를 사용하여 부동 소수점 예외를 마스크 또는 마스크 해제할 수도 있습니다.  
  
 `mask`의 값이 0인 경우 `_controlfp_s`는 부동 소수점 제어 단어를 가져와서 검색된 값을 `currentControl`에 저장합니다.  
  
 `mask`가 0이 아닌 경우 새 제어 단어의 새 값이 설정됩니다. `mask`에서 설정된 모든 비트(즉, 1과 같음)의 경우 `new`의 해당 비트가 제어 단어를 업데이트하는 데 사용됩니다. 즉, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) | (`new & mask`))입니다. 여기서 `fpcntrl`은 부동 소수점 제어 단어입니다. 이 시나리오에서 `currentControl`은 변경이 완료된 후의 값으로 설정됩니다. 그러나 이전 제어 단어 비트 값은 아닙니다.  
  
> [!NOTE]
>  기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 마스킹합니다.  
  
 `_controlfp_s`는 Intel(x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 및 ARM 플랫폼의 `_control87` 함수와 거의 동일합니다. X86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 또는 ARM 플랫폼을 대상으로 하는 경우 `_control87` 또는 `_controlfp_s`를 사용할 수 있습니다.  
  
 `_control87`과 `_controlfp_s` 간의 차이는 `DENORMAL` 값을 처리하는 방법에 있습니다. Intel(x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 및 ARM 플랫폼의 경우 `_control87`에서 DENORMAL OPERAND 예외 마스크를 설정하고 지울 수 있습니다. `_controlfp_s`는 DENORMAL OPERAND 예외 마스크를 수정하지 않습니다. 이 예제에서는 다음과 같은 차이를 보여 줍니다.  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 마스크 상수(`mask`)의 가능한 값 및 새 제어 값(`newControl`)은 아래의 16진수 값 테이블에 표시되어 있습니다. 16진수 값을 명시적으로 제공하는 대신 아래에 나열된 이식 가능 상수(`_MCW_EM`, `_EM_INVALID` 등)를 이러한 함수의 인수로 사용하세요.  
  
 Intel(x86) 파생 플랫폼에서는 하드웨어의 DENORMAL 입력 및 출력 값을 지원합니다. x86 동작은 DENORMAL 값을 유지하는 것입니다. SSE2를 지원하는 ARM 플랫폼 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼을 통해 DENORMAL 피연산자 및 결과가 플러시되거나 0으로 강제 적용될 수 있습니다. `_controlfp_s`, `_controlfp` 및 `_control87` 함수는 이 동작을 변경하는 마스크를 제공합니다. 다음 예제에서는 이 마스크의 사용을 보여 줍니다.  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM 플랫폼에서 `_controlfp_s` 함수는 FPSCR 레지스터에 적용됩니다. [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 MXCSR 레지스터에 저장되어 있는 SSE2 제어 단어만 영향을 받습니다. Intel(x86) 플랫폼에서 `_controlfp_s`는 x87 및 SSE2 모두에 대한 제어 단어(있는 경우)에 영향을 줍니다. 두 개의 제어 단어가 서로 일관되지 않을 수 있습니다(예를 들어 [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)에 대한 이전 호출로 인해). 두 제어 단어 간의 일관성이 없을 경우 `_controlfp_s`는 `currentControl`에서 `EM_AMBIGUOUS` 플래그를 설정합니다. 이는 반환된 제어 단어가 두 부동 소수점 제어 단어 모두의 상태를 정확히 나타내지 않을 수 있다는 경고입니다.  
  
 ARM 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서는 무한대 모드 또는 부동 소수점 정밀도를 변경할 수 없습니다. 정밀도 제어 마스크가 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에 사용되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수가 어설션을 실행하고 잘못된 매개 변수 처리기가 호출됩니다.  
  
 마스크가 올바르게 설정되지 않은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수에서 잘못된 매개 변수 예외를 생성합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `EINVAL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 사용 하는 경우이 함수는 무시 됩니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임 (CLR)에 기본 부동 소수점 정밀도만 지원 하기 때문에 컴파일할 수 있습니다.  
  
### <a name="mask-constants-and-values"></a>마스크 상수 및 값  
  
 `_MCW_EM` 마스크의 경우 마스크를 지우면 예외가 설정되며, 이를 통해 하드웨어 예외가 허용됩니다. 마스크를 설정하면 예외가 숨겨집니다. `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW`가 발생하면 다음 부동 소수점 명령이 실행될 때까지 하드웨어 예외가 throw됩니다. `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 직후에 하드웨어 예외를 생성하려면 FWAIT MASM 명령을 호출하세요.  
  
|마스크|16진수 값|상수|16진수 값|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN`(비정상 제어)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM`(인터럽트 예외 마스크)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC`(무한대 제어)<br /><br /> (ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서는 지원되지 않습니다.)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC`(반올림 제어)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC`(정밀도 제어)<br /><br /> (ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서는 지원되지 않습니다.)|0x00030000|`_PC_24`(24비트)<br /><br /> `_PC_53`(53비트)<br /><br /> `_PC_64`(64비트)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_controlfp_s`|\<float.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```C  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word;  
    int err;  
  
    // Show original FP control word and do calculation.  
    err = _controlfp_s(&control_word, 0, 0);  
    if ( err ) /* handle error here */;  
  
    printf( "Original: 0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "24-bit:   0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "Default:  0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)