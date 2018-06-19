---
title: rand_s | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand_s
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8407848db8f442324127df8d7267a5350c077b2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405759"
---
# <a name="rands"></a>rand_s

의사 난수를 생성합니다. 이 함수의 더 안전한 버전을는 [rand](rand.md)에 설명 된 대로 보안 향상 기능이 포함 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.

## <a name="syntax"></a>구문

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>매개 변수

*randomValue*<br/>
생성 된 값을 저장 하는 정수에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다. 하는 경우 입력된 포인터 _randomValue_ 가 null 포인터의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속 하려면 실행 허용 된 경우, 함수 반환 **EINVAL** 설정 **errno** 를 **EINVAL**합니다. 함수가 다른 이유로 실패 하는 경우 *_randomValue_ 0으로 설정 됩니다.

## <a name="remarks"></a>설명

**rand_s** 함수 범위 0에 있는 의사 난수 정수를 쓰고 **UINT_MAX** 입력된 포인터에 있습니다. **rand_s** 함수는 운영 체제를 사용 하 여 암호화 보안 난수를 생성 합니다. 에 의해 생성 된 초기값을 사용 하지 않습니다는 [srand](srand.md) 함수에 미치는 영향에서 사용 하는 난수 시퀀스 또는 [rand](rand.md)합니다.

**rand_s** 함수에는 해당 상수 필요 **_CRT_RAND_S** 다음 예제와 같이 선언 하려면 함수에 대해 포함 문 이전에 정의 합니다.

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** 에 따라 달라 집니다는 [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) 에서만 이상에서 Windows XP에서 사용할 수 있는 API입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>샘플 출력

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
[srand](srand.md)<br/>
