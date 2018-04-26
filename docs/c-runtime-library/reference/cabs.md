---
title: _cabs | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _cabs
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
- cabsl
- _cabs
- _cabsl
dev_langs:
- C++
helpviewer_keywords:
- cabs function
- cabsl function
- absolute values
- _cabsl function
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 345130fe72b7dd1ee416209c5702d877a036561c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="cabs"></a>_cabs

복소수의 절대값을 계산합니다.

## <a name="syntax"></a>구문

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>매개 변수

*z*<br/>
복소수입니다.

## <a name="return-value"></a>반환 값

**_cabs** 성공 하는 경우 해당 인수의 절대값을 반환 합니다. 오버플로에서 **_cabs** 반환 **HUGE_VAL** 설정 **errno** 를 **ERANGE**합니다. [_matherr](matherr.md)을 사용하여 오류 처리를 변경할 수 있습니다.

## <a name="remarks"></a>설명

**_cabs** 함수 형식의 구조 여야 하는 복잡 한 숫자의 절대값을 계산 [_complex](../../c-runtime-library/standard-types.md)합니다. 구조 *z* 는 실제 구성 요소로 이루어져 *x* 및 허수 구성 요소는 *y*합니다. 에 대 한 호출 **_cabs** 해당 하는 식의 값이 생성 `sqrt( z.x * z.x + z.y * z.y )`합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_cabs**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

#include <math.h>
#include <stdio.h>

int main( void )
{
   struct _complex number = { 3.0, 4.0 };
   double d;

   d = _cabs( number );
   printf( "The absolute value of %f + %fi is %f\n",
           number.x, number.y, d );
}
```

```Output
The absolute value of 3.000000 + 4.000000i is 5.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)   