---
title: rand_s | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rand_s
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
f1_keywords: rand_s
dev_langs: C++
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
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5fde51ee8fb65426166d9d5d2e7d6e5873dd6e8
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="rands"></a>rand_s

의사 난수를 생성합니다. 이 함수의 더 안전한 버전을는 [rand](../../c-runtime-library/reference/rand.md)에 설명 된 대로 보안 향상 기능이 포함 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다. 

## <a name="syntax"></a>구문

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>매개 변수

*randomValue*  
생성 된 값을 저장 하는 정수에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다. 하는 경우 입력된 포인터 _randomValue_ 가 null 포인터의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우 함수가 `EINVAL`를 반환하며 `errno`를 `EINVAL`로 설정합니다. 함수가 다른 이유로 실패 하는 경우 *_randomValue_ 0으로 설정 됩니다.

## <a name="remarks"></a>설명

`rand_s` 함수는 0부터 `UINT_MAX` 범위의 의사 난수 정수를 입력 포인터에 씁니다. `rand_s` 함수는 운영 체제를 사용하여 암호화된 보안 난수를 생성합니다. 이 함수는 [srand](../../c-runtime-library/reference/srand.md) 함수에서 생성한 시드를 사용하지 않으며, `rand`에서 사용하는 난수 시퀀스에도 영향을 주지 않습니다.

`rand_s` 함수에서는 다음 예제와 같이 선언하려는 함수의 포함문 앞에 상수 `_CRT_RAND_S`를 정의해야 합니다.

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

`rand_s`는 [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API에 따라 달라집니다(Windows XP 이상에서만 사용 가능함).

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`rand_s`|\<stdlib.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예

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

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
[srand](../../c-runtime-library/reference/srand.md)  
