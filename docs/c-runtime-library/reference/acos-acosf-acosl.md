---
title: acos, acosf, acosl | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- acosf
- acos
- acosl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- acos
- acosl
- acosf
- math/acosf
- math/acosl
dev_langs:
- C++
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5384d4e97ebb4f3f6152278e916c02bb350090ea
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401940"
---
# <a name="acos-acosf-acosl"></a>acos, acosf, acosl

아크코사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
```

```cpp
float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>매개 변수

*x*  
아크코사인 (역 코사인)을 계산 하는 1에서 1 사이의 값입니다.

## <a name="return-value"></a>반환 값

합니다 **acos** 의 아크코사인을 반환 하는 함수 *x* π 범위의 0입니다.

기본적으로 하는 경우 *x* -1 보다 작거나 1 보다 크면 **acos** 는 무한 한 값을 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± ∞|INVALID|_DOMAIN|
|± QNAN,IND|없음|_DOMAIN|
|&#124;x&#124;>1|INVALID|_DOMAIN|

## <a name="remarks"></a>설명

C + +에서는 오버 로드 하므로 오버 로드를 호출할 수 있습니다 **acos** 및 반환 하는 **float** 하 고 **긴** **double** 형식입니다. C 프로그램에서 **acos** 항상 받아서 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**acos**하십시오 **acosf**, **acosl**|\<math.h>|\<errno.h>|

## <a name="example"></a>예

이 프로그램에서 -1에서 1 사이 범위의 값을 묻는 메시지가 나타납니다. 이 범위를 벗어나는 입력 값은 `_DOMAIN` 오류 메시지를 생성합니다. 올바른 값을 입력하는 경우 프로그램에서 해당 값의 아크사인 및 아크코사인을 인쇄합니다.

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[asin, asinf, asinl](asin-asinf-asinl.md)  
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)  
[cos, cosf, cosl](cos-cosf-cosl.md)  
[_matherr](matherr.md)  
[sin, sinf, sinl](sin-sinf-sinl.md)  
[tan, tanf, tanl](tan-tanf-tanl.md)  