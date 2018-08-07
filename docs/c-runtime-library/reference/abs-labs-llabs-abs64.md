---
title: abs, labs, llabs, _abs64 | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- abs
- _abs64
- labs
- llabs
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
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
dev_langs:
- C++
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b783ee6e4a5ea511a26068ffb89fcc09236f20b1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408130"
---
# <a name="abs-labs-llabs-abs64"></a>abs, labs, llabs, _abs64

인수의 절대값을 계산합니다.

## <a name="syntax"></a>구문

```C
int abs( int n );
long labs( long n );
long long llabs( long long n );
__int64 _abs64( __int64 n );
```

```cpp
long abs( long n );   // C++ only
long long abs( long long n );   // C++ only
double abs( double n );   // C++ only
long double abs( long double n );   // C++ only
float abs( float n );   // C++ only
```

### <a name="parameters"></a>매개 변수

*n*  
숫자 값입니다.

## <a name="return-value"></a>반환 값

**abs**, **labs**를 **llabs** 고 **_abs64** 함수 매개 변수의 절대 값을 반환 *n*. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

C + +에서는 오버 로드 하므로 오버 로드를 호출할 수 있습니다 **abs** 및 반환 하는 **긴**하십시오 **긴** **긴**,  **부동 소수점**, **double**, 및 **long** **double** 값입니다. 이러한 오버로드는 \<cmath> 헤더에 정의됩니다. C 프로그램에서 **abs** 항상 받아서 반환 된 **int**합니다.

**Microsoft 전용**: 이러한 인수를 제공할 수는 모든 정수 계열 형식을 사용 하 여 나타낼 수 있는 음의 정수 범위가 해당 형식을 사용 하 여 나타낼 수 있는 양의 정수 범위 보다 크기 때문에 변환할 수 없는 함수입니다. 인수의 절대값을 반환 형식으로 표현할 수 없는 경우는 **abs** 함수 변경 되지 않은 인수 값을 반환 합니다. 특히 `abs(INT_MIN)`는 `INT_MIN`, `labs(LONG_MIN)`는 `LONG_MIN`, `llabs(LLONG_MIN)`는 `LLONG_MIN`, `_abs64(_I64_MIN)`는 `_I64_MIN`을 반환합니다. 즉 합니다 **abs** 양수 값을 보장 하기 위해 함수를 사용할 수 없습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|-----------------------|---------------------------|
|**abs**하십시오 **labs**, **llabs**|\<math.h> 또는 \<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> 또는 \<math.h>|
|**_abs64**|\<stdlib.h>|\<cstdlib> 또는 \<stdlib.h>|

오버 로드 된 버전을 사용 하도록 **abs** c + +에서 포함 해야 합니다는 \<cmath > 헤더입니다.

## <a name="example"></a>예

이 프로그램은 여러 숫자의 절대 값을 계산하여 표시합니다.

```C
// crt_abs.c
// Build: cl /W3 /TC crt_abs.c
// This program demonstrates the use of the abs function
// by computing and displaying the absolute values of
// several numbers.

#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <limits.h>

int main( void )
{
    int ix = -4;
    long lx = -41567L;
    long long llx = -9876543210LL;
    __int64 wx = -1;

    // absolute 32 bit integer value
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));

    // absolute long integer value
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));

    // absolute long long integer value
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));

    // absolute 64 bit integer value
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,
        _abs64(wx));

    // Integer error cases:
    printf_s("Microsoft implementation-specific results:\n");
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));
}
```

```Output
The absolute value of -4 is 4
The absolute value of -41567 is 41567
The absolute value of -9876543210 is 9876543210
The absolute value of 0xffffffffffffffff is 0x0000000000000001
Microsoft implementation-specific results:
abs(INT_MIN) returns -2147483648
labs(LONG_MIN) returns -2147483648
llabs(LLONG_MIN) returns -9223372036854775808
_abs64(_I64_MIN) returns 0x8000000000000000
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)  
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[_cabs](cabs.md)  
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)  
[imaxabs](imaxabs.md)  