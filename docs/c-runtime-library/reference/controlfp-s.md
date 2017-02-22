---
title: "_controlfp_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_controlfp_s"
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
  - "controlfp_s"
  - "_controlfp_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_controlfp_s 함수"
  - "controlfp_s 함수"
  - "EM_AMBIGUOUS"
  - "부동 소수점 함수, 제어 단어 설정"
  - "부동 소수점 숫자, 제어 단어"
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _controlfp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 컨트롤 단어를 가져오고 설정합니다.  이 버전의 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
## 구문  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### 매개 변수  
 `currentControl`  
 현재 제어 단어 비트 값입니다.  
  
 `newControl`  
 새 컨트롤 단어 비트 값입니다.  
  
 `mask`  
 새 컨트롤 단어 비트를 설정하기 위한 마스크입니다.  
  
## 반환 값  
 성공시 0이고, 혹은 실패 시 `errno` 입니다.  
  
## 설명  
 이 `_controlfp_s` 함수는, 부동 소수점 제어 단어에 `currentControl` 의 주소에 저장되어 얻고 `newControl` 을 사용하여 설정할 수 있는, 플랫폼 독립적이고 `_control87` 의 보다 안정적인 버전입니다.  값의 비트 부동 소수점 제어 상태를 나타냅니다.  부동 소수점 컨트롤 상태는 플랫폼에 따라 부동 소수점 연산 패키지에서 프로그램이 정밀도, 반올림, 인피니티 모드를 바꿀 수 있도록 합니다.  또한 `_controlfp_s` 를 부동 소수점 예외를 감추거나 나타내기 위해 사용할 수 있습니다.  
  
 0과 같은 `mask` 의 값의 경우, `_controlfp_s` 은 `currentControl` 의 검색된 값에 저장하고 부동 소수점 제어 단어를 얻습니다.  
  
 만약 `mask` 값이 0이 아니라면, 컨트롤 단어에 대한 새로운 값이 설정 됩니다. `mask`에 설정되어 있는 모든 비트\(즉, 값은 1\)에 대하여 `new` 에 해당하는 비트는 컨트롤 단어를 업데이트하기 위해 사용됩니다.  다른 말로, `fpcntrl` `=` \(\(`fpcntrl` `& ~mask`\) &#124; \(`new & mask`\)\). `fpcntrl` 는 부동 소수점 컨트롤 단어입니다.  이 시나리오에서는, `currentControl` 은 값으로 설정 변경 완료 이전 word 컨트롤 비트 값은 아닙니다.  
  
> [!NOTE]
>  기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 숨깁니다.  
  
 `_controlfp_s` 은 Intel \(x86\), `_control87`, ARM 플렛폼에서 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 함수와 거의 동일합니다.  x86을 대상으로 하는 경우, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], 혹은 ARM 플랫폼, `_control87` 혹은 `_controlfp_s` 을 사용할 수 있습니다.  
  
 이 `_control87` 과 `_controlfp_s` 사이의 다른 점은 `DENORMAL` 을 어떻게 처리하는가 입니다.  Intel \(x86\), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM 플랫폼에서 `_control87` 는 DENORMAL OPERAND 예외 마스크를 설정하고 선택 취소 할 수 있습니다.  `_controlfp_s` 는 DENORMAL OPERAND 예외 마스크를 수정하지 않습니다.  이 예제에서는 \_controlfp와 \_control87의 차이점을 설명합니다.  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 마스크 상수 \(`mask`\)와 새 컨트롤 값 \(`newControl`\) 에 가능한 값이 아래의 16진수 표에 나타나 있습니다.  명시적으로 16진수 값을 적용하시 보다는 \(`_MCW_EM`, `_EM_INVALID` 등\)에 있는 임시의 상수를 이 함수의 인수로 사용하십시오.  
  
 Intel \(x86\) 에서 파생된 플랫폼은 하드웨어에서 DENORMAL 입,출력 값을 지원합니다.  x86 작업은 DENORMAL 값을 저장하는 것입니다.  ARM 플랫폼과 SSE2 지원을 가진 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼은 DENORMAL 피연산자와 플러시되거나 0이 될 결과를 사용 할 수 있습니다.  이 `_controlfp_s`, `_controlfp`, `_control87` 함수는 작업을 변경하기 위해 마스크를 제공합니다.  다음 예제는 이 마스크의 사용을 보여줍니다:  
  
```  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM 플랫폼에서, `_controlfp_s` 함수는 FPSCR 레지스터에 적용합니다.  이 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서 MXCSR 레지스터에 저장된 SSE2 컨트롤 단어만 영향을 받습니다.  Intel \(x86\) 플랫폼에서 `_controlfp_s` 는 존재하는 x87과 SSE2에 대한 컨트롤 단어에 영향을 끼칩니다.  두 개의 제어 단어와 서로 일치 하지 않을 수 있습니다. \(예를 들어, [\_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)로 이전을 호출하기 때문에\). 두 개의 제어 단어 사이 일관성이 없는 경우, `_controlfp_s` 는 `currentControl` 에 `EM_AMBIGUOUS` 플래그를 설정합니다.  이것은 반환된 컨트롤 단어가 두 부동 소수점 컨트롤 단어의 상태를 정확하게 나타내지 않을 수도 있다는 경고 입니다.  
  
 ARM과 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처에서, 인피니티 모드 또는 부동 소수점 정밀도 변경은 지원하지 않습니다.  이 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에서 정밀도 컨트롤 마스크를 사용하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 만들어지는 동안에 함수는 어설션을 발생시키고 잘못된 매개변수 핸들러를 호출합니다.  
  
 마스크에 정확하게 설정되지 않은 경우, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 묘사된 잘못된 매개 변수 예외를 생성합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `EINVAL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 공용 언어 런타임\(CLR\)은 오직 기본 부동 소수점 정밀도만을 지원하기 때문에 이 함수는 컴파일 하기 위해 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 **\/clr:pure** 를 사용하는 경우 무시됩니다.  
  
 **16진수 값\(Hexadecimal Values\)**  
  
 이 `_MCW_EM` 마스크에 대해 이 정리는 하드웨어 예외를 허용하는 예외를 설정합니다. 이를 설정은 예외를 숨깁니다.  만약 `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 가 발생한 경우 하드웨어 예외가 부동 소수점 명령이 실행될 때 까지 throw되지 않습니다.  이 `_EM_UNDERFLOW` 또는 `_EM_OVERFLOW` 가 발생하고 난 다음 즉시 하드웨어 예외를 생성하고 싶다면, MASM 명령을 호출 하십시오.  
  
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
|`_controlfp_s`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
//  
  
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
  
## Output  
  
```  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)