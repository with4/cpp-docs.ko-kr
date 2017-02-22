---
title: "_control87, _controlfp, __control87_2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_control87"
  - "_controlfp"
  - "__control87_2"
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
  - "_control87"
  - "__control87_2"
  - "control87"
  - "_controlfp"
  - "controlfp"
  - "control87_2"
  - "_control87_2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__control87_2 함수"
  - "_control87 함수"
  - "_controlfp 함수"
  - "control87 함수"
  - "control87_2 함수"
  - "controlfp 함수"
  - "EM_AMBIGUOUS"
  - "부동 소수점 함수"
  - "부동 소수점 함수, 제어 단어 설정"
  - "부동 소수점 숫자, 제어 단어"
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# _control87, _controlfp, __control87_2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 컨트롤 단어를 가져오고 설정합니다.  보다 안전한 버전의 `_controlfp` 를 사용할 수 있습니다. [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md) 를 참고 하십시오.  
  
## 구문  
  
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
  
#### 매개 변수  
 `new`  
 새 컨트롤 단어 비트 값입니다.  
  
 `mask`  
 새 컨트롤 단어 비트를 설정하기 위한 마스크입니다.  
  
 `x86_cw`  
 x87 부동 소수점 단위에 컨트롤 단어로 채워집니다.  SSE2 컨트롤 단어만 설정 할 수 있도록 0 \(`NULL`\) 을 전달합니다.  
  
 `sse2_cw`  
 SSE 부동 소수점 단위에 대한 컨트롤 단어입니다.  x87 컨트롤 단어만 설정 할 수 있도록 0 \(`NULL`\) 을 전달합니다.  
  
## 반환 값  
 `_control87` 과 `_controlfp` 에 대하여, 반환 값에 있는 비트는 부동 소수점의 제어 상태를 나타냅니다.   `_control87` 에 의해 반환된 비트의 정의를 완료하려면, FLOAT.H를 참조 하십시오.  
  
 `__control87_2` 에 대한 반환 값 1은 성공을 의미합니다.  
  
## 설명  
 `_control87` 함수는 부동 소수점 컨트롤 단어를 가져오고 설정합니다.  부동 소수점 컨트롤 단어는 플랫폼에 따라 부동 소수점 연산 패키지에서 프로그램이 정밀도, 반올림, 인피니티 모드를 바꿀 수 있도록 합니다.  또한 `_control87` 를 부동 소수점 예외를 감추거나 나타내기 위해 사용할 수 있습니다.  만약 `mask` 값이 0이라면 `_control87` 은 부동 소수점 컨트롤 단어를 가져옵니다.  만약 `mask` 값이 0이 아니라면, 컨트롤 단어에 대한 새로운 값이 설정 됩니다. `mask`에 있는 모든 비트\(즉, 값은 1\)에 대하여 `new` 에 해당하는 비트는 컨트롤 단어를 업데이트하기 위해 사용됩니다.  다른 말로, `fpcntrl` `=` \(\(`fpcntrl` `& ~mask`\) &#124; \(`new & mask`\)\). `fpcntrl` 는 부동 소수점 컨트롤 단어입니다.  
  
> [!NOTE]
>  기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 숨깁니다.  
  
 `_controlfp` 는 `_control87` 의 휴대용 버전으로 독립 플렛폼입니다.  이것은 Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM 플렛폼에서 `_control87` 함수와 거의 동일합니다.  x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], 또는 ARM 플랫폼을 대상으로 하는 경우 `_control87` 또는 `_controlfp` 를 사용하십시오.  
  
 `_control87` 와 `_controlfp` 의 차이점은 DENORMAL 값을 어떻게 처리하느냐에 있습니다.  Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM 플랫폼에서 `_control87` 는 DENORMAL OPERAND 예외 마스크를 설정하고 선택 취소 할 수 있습니다.  `_controlfp` 는 DENORMAL OPERAND 예외 마스크를 수정하지 않습니다.  이 예제에서는 \_controlfp와 \_control87의 차이점을 설명합니다.  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 마스크 상수 \(`mask`\)와 새 컨트롤 값 \(`new`\) 에 가능한 값이 아래의 16진수 표에 나타나 있습니다.  명시적으로 16진수 값을 적용하시 보다는 \(`_MCW_EM`, `_EM_INVALID` 등\)에 있는 임시의 상수를 이 함수의 인수로 사용하십시오.  
  
 Intel \(x86\) 에서 파생된 플랫폼은 하드웨어에서 DENORMAL 입,출력 값을 지원합니다.  x86 작업은 DENORMAL 값을 저장하는 것입니다.  ARM 플랫폼과 SSE2 지원을 가진 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼은 DENORMAL 피연산자와 플러시되거나 0이 될 결과를 사용 할 수 있습니다.   `_controlfp` 와 `_control87` 함수는 작업을 변경하기 위해 마스크를 제공합니다.  다음 예제는 이 마스크의 사용을 보여줍니다.  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM 플랫폼에서 `_control87` 와 `_controlfp` 함수는 FPSCR 레지스터에 적용되는 함수입니다.  이 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 MXCSR 레지스터에 저장된 SSE2 컨트롤 단어만 영향을 받습니다.  Intel \(x86\) 플랫폼에서 `_control87` 와 `_controlfp` 는 존재하는 x87과 SSE2에 대한 컨트롤 단어에 영향을 끼칩니다.  함수 `__control87_2` 는 함께 또는 개별적으로 제어 될 수 있도록 x87 과 SSE2 부동 소수점 단위를 사용할 수 있습니다.  만약 두 단위에 모두 영향을 주려면, 정수 두개의 주소를 `x86_cw` 와 `sse2_cw` 에 전달합니다.  만약 하나의 단위에만 영향을 주고 싶다면, 해당 매개 변수에 대한 주소를 전달하고 남은 것에 대해 0 \(NULL\)을 전달합니다.  이러한 매개 변수 중 하나에 0이 전달 된 경우 함수는 부동 소수점 단위에 영향을 주지 않습니다.  이는 기능적으로 일부 코드에서 x87 부동 소수점 단위를 사용하고 나머지 부분에서 코드에서 SSE2 부동 소수점 단위를 사용하는 경우 유용할 수 있습니다.  만약 `__control87_2` 을 프로그램의 한부분에서 사용하고 부동 소수점 컨트롤 단어에 대한 다른 값을 설정한 후 `_control87` 또는 `_controlfp` 을 추가로 컨트롤 단어를 조작하기 위해 사용한다면, `_control87` 와 `_controlfp` 는 부동 소수점 단위의 상태를 나타내는 하나의 컨트롤 단어를 반환 하지 못할 수도 있습니다.  이런 경우, 이러한 함수는 두 컨트롤 단어 사이에 일관성이 없음을 나타내는 정수형 반환 값 내에 `EM_AMBIGUOUS` 플래그를 설정합니다.  이것은 반환된 컨트롤 단어가 두 부동 소수점 컨트롤 단어의 상태를 정확하게 나타내지 않을 수도 있다는 경고 입니다.  
  
 ARM과 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서, 인피니티 모드 또는 부동 소수점 정밀도 변경은 지원하지 않습니다.  이 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서 정밀도 컨트롤 마스크를 사용하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 만들어지는 동안에 함수는 어설션을 발생시키고 잘못된 매개변수 핸들러를 호출합니다.  
  
> [!NOTE]
>  `__control87_2` 는 ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서는 지원하지 않습니다.  사용 하는 경우 `__control87_2` 프로그램은 ARM에 대 한 컴파일 및 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 컴파일 하는 경우 컴파일러는 오류를 생성합니다.  
  
 공용 언어 런타임\(CLR\)은 오직 기본 부동 소수점 정밀도만을 지원하기 때문에 이러한 함수는 컴파일 하기 위해 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 `/clr:pure` 를 사용하는 경우 무시됩니다.  
  
 **16진수 값\(Hexadecimal Values\)**  
  
 `_MCW_EM` 마스크에 대해 마스크 정리는 하드웨어 예외를 허용하는 예외를 설정합니다. 마스크를 설정은 예외를 숨깁니다.  만약 `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 가 발생한 경우 하드웨어 예외가 부동 소수점 명령이 실행될 때 까지 throw되지 않습니다.   `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 가 발생하고 난 다음 즉시 하드웨어 예외를 생성하고 싶다면, `FWAIT` MASM 명령을 호출 하십시오.  
  
|마스크|16진수\(Hex value\)|상수|16진수\(Hex value\)|  
|---------|-----------------------|--------|-----------------------|  
|`_MCW_DN` \(Denormal control\)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` \(Interrupt exception mask\)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` \(Infinity control\)<br /><br /> \(ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서 지원하지 않습니다.\)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` \(Rounding control\)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` \(Precision control\)<br /><br /> \(ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서 지원하지 않습니다.\)|0x00030000|`_PC_24` \(24 bits\)<br /><br /> `_PC_53` \(53 bits\)<br /><br /> `_PC_64` \(64 bits\)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_control87`, `_controlfp`, `_control87_2`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
//  
  
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
  
## Output  
  
```  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md)