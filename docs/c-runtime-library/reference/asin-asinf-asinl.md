---
title: asin, asinf, asinl | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
dev_langs:
- C++
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dd1399042e1055d124cd3c53363a6979d4256d3
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

아크사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
아크사인을 계산해야 하는 값입니다.

## <a name="return-value"></a>반환 값

**asin** 함수 (역 사인 함수)의 아크사인을 반환 *x* π/2 라디안으로 범위-π/2에서입니다.

기본적으로 경우 *x* 가-1 보다 작거나 1 보다 큰 경우 **asin** 는 무한를 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± ∞|**올바르지 않음**|**_DOMAIN**|
|± **QNAN**, **IND**|없음|**_DOMAIN**|
|&#124;x&#124;>1|**올바르지 않음**|**_DOMAIN**|

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **asin** 와 **float** 및 **긴** **double** 값입니다. C 프로그램에서 **asin** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="example"></a>예제

자세한 내용은 [acos, acosf, acosl](acos-acosf-acosl.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
