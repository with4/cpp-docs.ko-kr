---
title: _control87, _controlfp, __control87_2 | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 098e5760718e4e2d2a9063700b09d0381e76df1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

부동 소수점 제어 단어를 가져와서 설정합니다. 더 안전한 버전 **_controlfp** 이름은 사용할 수 있으며 참조 [_controlfp_s](controlfp-s.md)합니다.

## <a name="syntax"></a>구문

```C
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

### <a name="parameters"></a>매개 변수

*new*<br/>
새 제어 단어 비트 값입니다.

*마스크*<br/>
설정할 새 제어 단어 비트의 마스크입니다.

*x86_cw*<br/>
x87 부동 소수점 유닛에 대한 제어 단어로 채워집니다. 0을 전달 (**NULL**) SSE2 제어 단어만 설정할 수 있습니다.

*sse2_cw*<br/>
SSE 부동 소수점 유닛에 대한 제어 단어입니다. 0 전달 (**NULL**)는 x87를 설정 하려면 단어를 제어 합니다.

## <a name="return-value"></a>반환 값

에 대 한 **_control87** 및 **_controlfp**, 값의 비트 부동 소수점 제어 상태를 나타내는 반환 합니다. 반환 되는 비트의 완전 한 정의 대 한 **_control87**, FLOAT를 참조 하십시오. 8.

에 대 한 **__control87_2**, 반환 값은 1이 성공 했음을 의미입니다.

## <a name="remarks"></a>설명

**_control87** 함수 가져오고 부동 소수점 제어 단어를 설정 합니다. 부동 소수점 제어 단어를 사용하면 프로그램이 플랫폼에 따라 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. 사용할 수도 있습니다 **_control87** 마스크 또는 부동 소수점 예외를 마스크 해제 합니다. 경우에 대 한 값 *마스크* 0은 **_control87** 부동 소수점 제어 단어를 가져옵니다. 경우 *마스크* 은 제어 단어에 대 한 새 값을 0이 아니면 설정 되어:에 있는 모든 비트에 대 한 (즉, 1 같음)에서 *마스크*의 해당 비트가 *새* 컨트롤을 업데이트 하는 데 사용 됩니다 단어입니다. 즉, **fpcntrl** = ((**fpcntrl** & ~*마스크*) &#124; (*새* & *마스크*)) 여기서 **fpcntrl** 부동 소수점 제어 단어입니다.

> [!NOTE]
> 기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 마스킹합니다.

**_controlfp** 의 플랫폼 독립적 이며 휴대용 버전이 **_control87**합니다. 와 거의 동일는 **_control87** x86, x64 및 ARM 플랫폼에 대해 함수입니다. X86, x64 또는 ARM 플랫폼 대상으로 하는, 사용 하 여 **_control87** 또는 **_controlfp**합니다.

차이 **_control87** 및 **_controlfp** 비정상적인 값을 처리 하는 방법에 있습니다. X86, x64 및 ARM 플랫폼에 대 한 **_control87** 설정 하 고 비정상적인 피연산자 예외 마스크의 선택을 취소 합니다. **_controlfp** 비정상적인 피연산자 예외 마스크를 수정 하지는 않습니다. 이 예제에서는 다음과 같은 차이를 보여 줍니다.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

마스크 상수에 대 한 가능한 값 (*마스크*) 하 고 새 컨트롤 값 (*새*) 16 진수 값은 다음과 같습니다. 아래에 나열 된 휴대용 상수를 사용 하 여 (**_MCW_EM**, **_EM_INVALID**, 등)이이 함수에 인수로 16 진수를 제공 하는 대신 값을 명시적으로 합니다.

Intel x86 파생 플랫폼 비정상적인 입력을 지원 하 고 하드웨어의 값을 출력 합니다. x86 동작은 DENORMAL 값을 유지하는 것입니다. SSE2 플랫폼 지원 x64 및 ARM 플랫폼 비정상적인 피연산자와 결과를 플러시 하거나 0으로 강제를 사용 하도록 설정 합니다. **_controlfp** 및 **_control87** 함수가이 동작을 변경 하는 마스크를 제공 합니다. 다음 예제에서는 이 마스크의 사용을 보여 줍니다.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM 플랫폼에서 **_control87** 및 **_controlfp** 함수 고 FPSCR 레지스터에 적용 합니다. X64 아키텍처에서는 저장 된 SSE2 제어 단어만는 MXCSR 레지스터에 영향을 합니다. X86 플랫폼에서 **_control87** 및 **_controlfp** 있는 경우는 x87와 SSE2에 대 한 제어 단어에 영향을 줍니다. 함수 **__control87_2** 는 x87와 함께 또는 개별적으로 제어할 수 SSE2 부동 소수점 단위로 사용 하도록 설정 합니다. 두 개의 정수를 주소에 전달 하는 두 장치에 영향을 하려는 경우 **x86_cw** 및 **sse2_cw**합니다. 하나의 유닛에만 영향을 주려는 경우 해당 매개 변수에 대해서는 주소를 전달하지만 다른 매개 변수에 대해서는 0(NULL)을 전달합니다. 이러한 매개 변수 중 하나에 대해 0을 전달하면 함수가 부동 소수점 유닛에는 영향을 주지 않습니다. 이 기능은 코드의 일부에서 x87 부동 소수점 유닛을 사용하고 유닛의 다른 부분에서는 SSE2 부동 소수점 유닛을 사용하는 경우에 유용할 수 있습니다. 사용 하는 경우 **__control87_2** 프로그램의 한 부분에 있는 부동 소수점 제어 단어에 대 한 다른 값을 설정 하 고 다음 **_control87** 또는 **_controlfp** 추가로 그런 다음 제어 단어를 조작 **_control87** 및 **_controlfp** 부동 소수점 두 장치 상태를 나타내는 단일 제어 단어를 반환할 수 수 있습니다. 이 경우 이러한 함수는 다음과 같이 설정 됩니다.는 **EM_AMBIGUOUS** 두 개의 제어 단어 사이 불일치가 임을 나타내기 위해 반환 된 정수 값에 대 한 플래그입니다. 이는 반환된 제어 단어가 두 부동 소수점 제어 단어 모두의 상태를 정확히 나타내지 않을 수 있다는 경고입니다.

ARM 및 x64 아키텍처에서는 무한대 모드 또는 부동 소수점 전체 자릿수를 변경할 수 없습니다. 정밀도 컨트롤 마스크 x64에 사용 되는 경우 플랫폼에 함수를 어설션을 발생 시키고에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

> [!NOTE]
> **__control87_2** 는 ARM 또는 x64 지원 되지 않습니다 아키텍처. 사용 하는 경우 **__control87_2** 은 ARM 또는 x64에 대 한 프로그램을 컴파일하면 및 아키텍처에서는 컴파일러 오류가 발생 합니다.

사용 하는 경우 이러한 함수는 무시 됩니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임 (CLR)에 기본 부동 소수점 정밀도만 지원 하기 때문에 컴파일할 수 있습니다.

**16진수 값**

에 대 한는 **_MCW_EM** / / 마스크 선택을 취소 하면 마스크 설정 수는 하드웨어 예외는 예외, 예외를 숨기는 마스크를 설정 합니다. 경우는 **_EM_UNDERFLOW** 또는 **_EM_OVERFLOW** 발생 다음 부동 소수점 명령이 실행 될 때까지 하드웨어 예외가 throw 됩니다. 하드웨어 예외를 생성 하려면 직후 **_EM_UNDERFLOW** 또는 **_EM_OVERFLOW**, 호출의 **FWAIT** MASM 명령입니다.

|마스크|16진수 값|상수|16진수 값|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (비정상적인 컨트롤)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (인터럽트 예외 마스크)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (무한대 컨트롤)<br /><br /> (ARM 또는 x64에서는 지원 되지 않음] 플랫폼입니다.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (반올림 컨트롤)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (정밀도 컨트롤)<br /><br /> (지원 되지 않음 ARM 또는 x64 플랫폼.)|0x00030000|**_PC_24** (24 비트)<br /><br /> **_PC_53** (53 비트)<br /><br /> **_PC_64** (64 비트)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

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

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
