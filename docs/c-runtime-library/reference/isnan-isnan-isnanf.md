---
title: isnan, _isnan, _isnanf | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8552f59bc0d49ebae0d4a534225af5d9f5facb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf

부동 소수점 값이 NAN(숫자가 아님)인지를 테스트합니다.

## <a name="syntax"></a>구문

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

C에서는 **isnan** 매크로 및 **_isnan** 및 **_isnanf** 함수 0이 아닌 값을 반환 하는 경우 인수 *x* nan 고, 그렇지 않으면은 0을 반환 합니다.

C + +에서는 **isnan** 템플릿 함수 반환 **true** 경우 인수 *x* nan; 반환 하지 않으면 **false**합니다.

## <a name="remarks"></a>설명

C **isnan** 매크로 및 **_isnan** 및 **_isnanf** 부동 소수점 값을 테스트 하는 함수 *x*, 경우에 0이 아닌 값을 반환 *x* 값이 nan (숫자가 번호) 값입니다. NAN은 지정된 형식에 대해 부동 소수점 연산의 결과를 IEEE-754 부동 소수점 형식으로 나타낼 수 없는 경우 생성됩니다. 출력에 NAN이 나타나는 방법에 대한 자세한 내용은 [printf](printf-printf-l-wprintf-wprintf-l.md)를 참조하세요.

C + +를 컴파일할 때는 **isnan** 매크로 정의 하지 않은 및 **isnan** 템플릿 함수 대신 정의 됩니다. 형식의 값을 반환 **bool** 정수 대신 합니다.

**_isnan** 및 **_isnanf** 함수는 Microsoft 전용입니다. **_isnanf** 기능은 x64 컴파일 되었을 때 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**, **_isnanf**|\<math.h>|\<math.h> 또는 \<cmath>|
|**_isnan**|\<float.h>|\<float.h> 또는 \<cfloat>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
