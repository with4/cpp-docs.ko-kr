---
title: _status87, _statusfp, _statusfp2 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69297d7ff1e3ec40cfe4fc22dec86c356d1697d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

부동 소수점 상태 단어를 가져옵니다.

## <a name="syntax"></a>구문

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>매개 변수

*px86*<br/>
이 주소에는 x87 부동 소수점 단위의 상태 단어가 채워집니다.

*pSSE2*<br/>
이 주소에는 SSE2 부동 소수점 단위의 상태 단어가 채워집니다.

## <a name="return-value"></a>반환 값

에 대 한 **_status87** 및 **_statusfp**, 반환 되는 값의 비트 부동 소수점 상태를 나타냅니다. 부동 소수점을 참조 하십시오. 반환 되는 비트의 정의 대 한 파일을 포함 하는 H **_statusfp**합니다. 대부분의 수학 라이브러리 함수는 부동 소수점 상태 단어를 수정하는데, 이 경우 예기치 않은 결과가 발생합니다. 최적화 수 순서를 변경, 결합 및 제거에 대 한 호출 주위 부동 소수점 연산 **_status87**, **_statusfp**, 및 관련 함수입니다. 부동 소수점 연산을 다시 정렬하는 최적화가 수행되지 않도록 하려면 [/Od (Disable (Debug))](../../build/reference/od-disable-debug.md) 컴파일러 옵션 또는 [fenv_access](../../preprocessor/fenv-access.md) pragma 지시문을 사용합니다. 반환 값의 **_clearfp** 및 **_statusfp**, 및의 반환 매개 변수 또한 **_statusfp2**, 더 적은 부동 소수점 작업이 수행 될 경우 신뢰할 수 사이의 부동 소수점 상태 단어의 알려진된 상태입니다.

## <a name="remarks"></a>설명

**_statusfp** 함수는 부동 소수점 상태 단어를 가져옵니다. 상태 단어는 부동 소수점 프로세서 상태와 부동 소수점 예외 처리기에서 검색한 기타 조건(예: 부동 소수점 스택 오버플로 및 언더플로)의 조합입니다. 상태 단어의 내용을 반환하기 전에 마스킹되지 않은 예외를 확인합니다. 즉, 호출자에게 보류 중인 예외를 알립니다. X86 플랫폼에서 **_statusfp** 는 x87와 SSE2 부동 소수점 상태를 반환 합니다. x64 플랫폼에서 반환되는 상태는 SSE의 MXCSR 상태를 기준으로 합니다. ARM 플랫폼에서는 **_statusfp** 고 FPSCR 레지스터에서 상태를 반환 합니다.

**_statusfp** 의 플랫폼 독립적 이며 휴대용 버전이 **_status87**합니다. 동일 **_status87** (x86) Intel 플랫폼에서 x64 및 ARM 플랫폼에서 지원 됩니다. 부동 소수점 코드를 모든 아키텍처에 이식 하려면 사용 하 여 **_statusfp**합니다. 경우에 x86 플랫폼에서 사용할 수 있습니다 **_status87** 또는 **_statusfp**합니다.

권장 **_statusfp2** (예: Pentium IV)는 x87와 SSE2 부동 소수점 프로세서를 모두 포함 된 칩에 대 한 합니다. 에 대 한 **_statusfp2**, 부동 소수점 상태 단어는 x87 또는 SSE2 부동 소수점 프로세서를 모두 사용 하 여 주소가 채워집니다. 지 원하는 x87 부동 소수점 프로세서 SSE2 칩에 대 한 EM_AMBIGUOUS 경우 1로 설정 되어 **_statusfp** 또는 **_controlfp** 사용 되는 x87 또는 SSE2를 참조할 수 있으므로 작업은 모호 합니다. 부동 소수점 상태 단어입니다. **_statusfp2** 함수 에서만 x86 플랫폼입니다.

이러한 함수에 대 한 유용 하지 않은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임 (CLR)에 기본 부동 소수점 정밀도만 지원 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
