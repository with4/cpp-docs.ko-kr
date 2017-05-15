---
title: "_control87, _controlfp, __control87_2 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 34
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 25dfd357f0b3385f1e9bdcc4249ad3cf4399e0b6
ms.contentlocale: ko-kr
ms.lasthandoff: 02/28/2017

---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2
부동 소수점 제어 단어를 가져와서 설정합니다. `_controlfp`의 더 안전한 버전을 사용할 수 있습니다. [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned int _control87(   
   unsigned int new,  
   unsigned int mask   
);  
unsigned int _controlfp(   
   unsigned int new,  
   unsigned int mask   
);  
int __control87_2(  
   unsigned int new,  
   unsigned int mask,  
   unsigned int* x86_cw,  
   unsigned int* sse2_cw  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `new`  
 새 제어 단어 비트 값입니다.  
  
 `mask`  
 설정할 새 제어 단어 비트의 마스크입니다.  
  
 `x86_cw`  
 x87 부동 소수점 유닛에 대한 제어 단어로 채워집니다. 0(`NULL`)을 전달하여 SSE2 제어 단어만 설정할 수 있습니다.  
  
 `sse2_cw`  
 SSE 부동 소수점 유닛에 대한 제어 단어입니다. 0(`NULL`)을 전달하여 x87 제어 단어만 설정할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 `_control87` 및 `_controlfp`의 경우 반환되는 값의 비트는 부동 소수점 제어 상태를 나타냅니다. `_control87`에서 반환된 비트의 전체 정의를 보려면 FLOAT.H를 참조하세요.  
  
 `__control87_2`의 경우 반환 값은 성공을 나타내는 1입니다.  
  
## <a name="remarks"></a>설명  
 `_control87` 함수는 부동 소수점 제어 단어를 가져와서 설정합니다. 부동 소수점 제어 단어를 사용하면 프로그램이 플랫폼에 따라 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. `_control87`를 사용하여 부동 소수점 예외를 마스크 또는 마스크 해제할 수도 있습니다. `mask`의 값이 0인 경우 `_control87`은 부동 소수점 제어 단어를 가져옵니다. `mask`가 0이 아닌 경우 새 제어 단어의 새 값이 설정됩니다. `mask`에서 켜져 있는 모든 비트(즉, 1과 같음)의 경우 `new`의 해당 비트가 제어 단어를 업데이트하는 데 사용됩니다. 즉, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) | (`new & mask`))입니다. 여기서 `fpcntrl`은 부동 소수점 제어 단어입니다.  
  
> [!NOTE]
>  기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 마스킹합니다.  
  
 `_controlfp`는 플랫폼 독립적이며 `_control87`의 이식 가능한 버전입니다. Intel(x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 및 ARM 플랫폼의 `_control87` 함수와 거의 동일합니다. X86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 또는 ARM 플랫폼을 대상으로 하는 경우 `_control87` 또는 `_controlfp`를 사용하세요.  
  
 `_control87`과 `_controlfp` 간의 차이는 DENORMAL 값을 처리하는 방법에 있습니다. Intel(x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 및 ARM 플랫폼의 경우 `_control87`에서 DENORMAL OPERAND 예외 마스크를 설정하고 지울 수 있습니다. `_controlfp`는 DENORMAL OPERAND 예외 마스크를 수정하지 않습니다. 이 예제에서는 다음과 같은 차이를 보여 줍니다.  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 마스크 상수(`mask`)의 가능한 값 및 새 제어 값(`new`)은 아래의 16진수 값 테이블에 표시되어 있습니다. 16진수 값을 명시적으로 제공하는 대신 아래에 나열된 이식 가능 상수(`_MCW_EM`, `_EM_INVALID` 등)를 이러한 함수의 인수로 사용하세요.  
  
 Intel(x86) 파생 플랫폼에서는 하드웨어의 DENORMAL 입력 및 출력 값을 지원합니다. x86 동작은 DENORMAL 값을 유지하는 것입니다. SSE2를 지원하는 ARM 플랫폼 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼을 통해 DENORMAL 피연산자 및 결과가 플러시되거나 0으로 강제 적용될 수 있습니다. `_controlfp` 및 `_control87` 함수는 이 동작을 변경하는 마스크를 제공합니다. 다음 예제에서는 이 마스크의 사용을 보여 줍니다.  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM 플랫폼에서 `_control87` 및 `_controlfp` 함수는 FPSCR 레지스터에 적용됩니다. [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 MXCSR 레지스터에 저장되어 있는 SSE2 제어 단어만 영향을 받습니다. Intel(x86) 플랫폼에서 `_control87` 및 `_controlfp`는 x87 및 SSE2 모두에 대한 제어 단어(있는 경우)에 영향을 줍니다. `__control87_2` 함수를 사용하여 x87 및 SSE2 부동 소수점 유닛을 함께 또는 별도로 제어할 수 있습니다. 두 개의 유닛에 영향을 주려는 경우 두 정수의 주소를 `x86_cw` 및 `sse2_cw`에 전달합니다. 하나의 유닛에만 영향을 주려는 경우 해당 매개 변수에 대해서는 주소를 전달하지만 다른 매개 변수에 대해서는 0(NULL)을 전달합니다. 이러한 매개 변수 중 하나에 대해 0을 전달하면 함수가 부동 소수점 유닛에는 영향을 주지 않습니다. 이 기능은 코드의 일부에서 x87 부동 소수점 유닛을 사용하고 유닛의 다른 부분에서는 SSE2 부동 소수점 유닛을 사용하는 경우에 유용할 수 있습니다. 프로그램의 한 부분에서 `__control87_2`를 사용하며 부동 소수점 제어 단어에 대해 다른 값을 설정한 다음 `_control87` 또는 `_controlfp`를 사용하여 제어 단어를 더 조작하면 `_control87` 및 `_controlfp`에서 두 부동 소수점 유닛의 상태를 나타내는 단일 제어 단어를 반환할 수 없습니다. 이 경우 이러한 함수는 두 개의 제어 단어 간의 불일치가 있음을 나타내기 위해 반환된 정수 값의 `EM_AMBIGUOUS` 플래그를 설정합니다. 이는 반환된 제어 단어가 두 부동 소수점 제어 단어 모두의 상태를 정확히 나타내지 않을 수 있다는 경고입니다.  
  
 ARM 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서는 무한대 모드 또는 부동 소수점 정밀도를 변경할 수 없습니다. 정밀도 제어 마스크가 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에 사용되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수가 어설션을 실행하고 잘못된 매개 변수 처리기가 호출됩니다.  
  
> [!NOTE]
>  `__control87_2`는 ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 지원되지 않습니다. `__control87_2`를 사용하고 ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처용 프로그램을 컴파일하는 경우 컴파일러에서 오류를 생성합니다.  
  
 사용 하는 경우 이러한 함수는 무시 됩니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임 (CLR)에 기본 부동 소수점 정밀도만 지원 하기 때문에 컴파일할 수 있습니다.  
  
 **16진수 값**  
  
 `_MCW_EM` 마스크의 경우 마스크를 지우면 예외가 설정되며, 이를 통해 하드웨어 예외가 허용됩니다. 마스크를 설정하면 예외가 숨겨집니다. `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW`가 발생하면 다음 부동 소수점 명령이 실행될 때까지 하드웨어 예외가 throw됩니다. `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 직후에 하드웨어 예외를 생성하려면 `FWAIT` MASM 명령을 호출하세요.  
  
|마스크|16진수 값|상수|16진수 값|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN`(비정상 제어)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM`(인터럽트 예외 마스크)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC`(무한대 제어)<br /><br /> (ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서는 지원되지 않습니다.)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC`(반올림 제어)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC`(정밀도 제어)<br /><br /> (ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서는 지원되지 않습니다.)|0x00030000|`_PC_24`(24비트)<br /><br /> `_PC_53`(53비트)<br /><br /> `_PC_64`(64비트)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_control87`, `_controlfp`, `_control87_2`|\<float.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```C  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word_x87;  
  
    // Show original x87 control word and do calculation.  
    control_word_x87 = __control87_2(0, 0,  
                                     &control_word_x87, 0);  
    printf( "Original: 0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    control_word_x87 = __control87_2(_PC_24, MCW_PC,  
                                     &control_word_x87, 0);  
    printf( "24-bit:   0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,   
                                     &control_word_x87, 0 );  
    printf( "Default:  0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)
