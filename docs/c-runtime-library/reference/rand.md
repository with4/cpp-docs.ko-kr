---
title: rand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rand
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
f1_keywords: rand
dev_langs: C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aada39e6ea3de3cae65642d29fa1b5ce4bad098e
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="rand"></a>rand

잘 알려진을 완벽 하 게 재현할 수 있는 알고리즘을 사용 하 여 난수를 생성 합니다. 이 함수는 프로그래밍 방식으로 더 안전한 버전을 사용할 수 있습니다. 참조 [rand_s](../../c-runtime-library/reference/rand-s.md)합니다. 에 의해 생성 된 숫자 `rand` 암호로 보호 되지 않습니다. 자세히 난수 생성 암호화 보안을 사용 하 여 `rand_s` 에서 c + + 표준 라이브러리에 선언 된 함수 또는 [ \<임의 >](../../standard-library/random.md)합니다.

## <a name="syntax"></a>구문

```C
int rand( void );
```

## <a name="return-value"></a>반환 값

`rand`는 위에서 설명한 대로 의사 난수를 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

`rand` 함수는 0부터 `RAND_MAX`(32767) 범위의 의사 난수 정수를 반환합니다. `rand`를 호출하기 전에 의사 난수 생성기를 시드하려면 [srand](../../c-runtime-library/reference/srand.md) 함수를 사용합니다.

`rand` 함수는 잘 알려진 시퀀스를 생성 하 고 암호화 기능이로 사용 하기에 적합 하지 않습니다. 자세히 난수 생성 암호화 보안을 사용 하 여 `rand_s` 에서 c + + 표준 라이브러리에 선언 된 함수 또는 [ \<임의 >](../../standard-library/random.md)합니다. `rand()`의 문제와 `<random>`에서 이러한 문제를 해결하는 방법에 대한 자세한 내용은 [이 비디오](http://go.microsoft.com/fwlink/?LinkId=397615)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`rand`|\<stdlib.h>|

호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.

## <a name="example"></a>예

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
 3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[srand](../../c-runtime-library/reference/srand.md)  
[rand_s](../../c-runtime-library/reference/rand-s.md)  