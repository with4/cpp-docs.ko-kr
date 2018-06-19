---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
dev_langs:
- C++
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1561e93fc19832607d304f3d087ab33b04040de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401924"
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

정수가 식별자로 사용할 수 있는 문자를 나타내는지 여부를 결정합니다.

## <a name="syntax"></a>구문

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다. *c* 함수의 좁은 문자 버전에 대 한 0-255 범위에 있어야 합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

둘 다 **__iscsym** 및 **__iswcsym** 경우 0이 아닌 값을 반환 *c* 문자, 밑줄 또는 숫자인 됩니다. 둘 다 **__iscsymf** 및 **__iswcsymf** 경우 0이 아닌 값을 반환 *c* 문자 또는 밑줄은 합니다. 이러한 각 루틴 0을 반환 *c* 테스트 조건을 만족 하지 않습니다. 있는 이러한 함수 버전은 **_l** 접미사를 사용 하는 점을 제외 하면 동일는 *로캘* 은 로캘 종속 동작에 현재 로캘 대신 전달 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="remarks"></a>설명

전처리기 매크로 _CTYPE_DISABLE_MACROS가 정의되지 않은 경우 이러한 루틴은 매크로로 정의됩니다. 이러한 루틴의 매크로 버전을 사용하는 경우 인수를 두 번 이상 평가할 수 있습니다. 인수 목록 내에서 의도하지 않은 결과를 생성하는 식을 사용할 때는 주의해야 합니다.

이전 버전과 호환성을 위해 **iscsym** 및 **iscsymf** 매크로로 정의 된 경우에만 [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) 이 정의 되지 않았거나 정의 으로 0; 그렇지 않으면 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**iscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|C: \<ctype.h><br /><br /> C++: \<cctype> 또는 \<ctype.h>|

**iscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__ iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, 및 **_iswcsymf_l** 루틴은 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
