---
title: div, ldiv, lldiv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- div
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
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3a0e28030b62f68d478cb976b1f89d91904655a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="div-ldiv-lldiv"></a>div, ldiv, lldiv

두 정수 값의 몫과 나머지를 계산합니다.

## <a name="syntax"></a>구문

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*번호*<br/>
분자입니다.

*denom*<br/>
분모입니다.

## <a name="return-value"></a>반환 값

**div** 형식의 인수를 사용 하 여 호출 **int** 형식의 구조를 반환 **div_t**, 몫과 나머지로 구성 된 합니다. 형식의 인수를 사용 하는 반환 값 **긴** 은 **ldiv_t**, 인수 형식의 반환 값과 **긴** **긴** 는**lldiv_t**합니다. **div_t**, **ldiv_t**, 및 **lldiv_t** 에 정의 된 \<stdlib.h > 합니다.

## <a name="remarks"></a>설명

**div** 나눕니다 함수 *번호* 여 *denom* 함으로써 몫과 나머지를 계산 하 고 있습니다. [div_t](../../c-runtime-library/standard-types.md) 구조에는 몫인 **q u o t**, 및 나머지 인 **rem**합니다. 몫의 부호는 수학적 몫의 부호와 같습니다. 몫의 절대 값은 수학적 몫의 절대 값보다 작은 가장 큰 정수입니다. 분모가 0이면 프로그램이 종료되고 오류 메시지가 표시됩니다.

오버 로드 **div** 형식의 인수를 사용 하는 **긴** 또는 **긴** **긴** 은 c + + 코드에 사용할 수 있습니다. 반환 형식 [ldiv_t](../../c-runtime-library/standard-types.md) 및 [lldiv_t](../../c-runtime-library/standard-types.md) 멤버가 포함 되어 **q u o t** 및 **rem**, 의멤버와동일한의미를갖는**div_t**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
