---
title: fpclassify | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.topic: reference
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da55cb87804d178d5a305ed466aa498de4bc1ee5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fpclassify"></a>fpclassify

인수의 부동 소수점 분류를 반환합니다.

## <a name="syntax"></a>구문

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only

```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**fpclassify** 인수의 부동 소수점 클래스를 나타내는 정수 값을 반환 *x*합니다. 이 테이블에서 반환 된 가능한 값을 보여 줍니다. **fpclassify**에 정의 된 \<math.h > 합니다.

|값|설명|
|-----------|-----------------|
|**FP_NAN**|자동, 신호 또는 비활성화 상태 NaN|
|**FP_INFINITE**|양수 또는 음수 무한대|
|**FP_NORMAL**|정규화된 0이 아닌 양수 또는 음수 값|
|**FP_SUBNORMAL**|비정규화된 양수 또는 음수 값|
|**FP_ZERO**|양수 또는 음수 0 값|

## <a name="remarks"></a>설명

C에서는 **fpclassify** 매크로; c + +에서는 **fpclassify** 유형의 인수를 사용 하 여 오버 로드 된 함수는 **float**, **double**, 또는 **긴** **double**합니다. 두 경우 모두 반환되는 값은 인수 식의 유효 형식에 따라 결정되고 중간 표현의 영향은 받지 않습니다. 일반적인 예를 들어 **double** 또는 **긴** **double** 값 수는 무한대 될, 비정상적인, 또는로 변환 하는 경우 값 0을 **float**합니다.

## <a name="requirements"></a>요구 사항

|함수/매크로|필수 헤더(C)|필수 헤더(C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> 또는 \<cmath>|

**fpclassify** 매크로 및 **fpclassify** ISO C99 및 C + + 11 사양에 맞게 함수입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
