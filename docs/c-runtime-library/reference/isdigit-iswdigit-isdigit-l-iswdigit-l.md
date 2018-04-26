---
title: isdigit, iswdigit, _isdigit_l, _iswdigit_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _isdigit_l
- iswdigit
- _iswdigit_l
- isdigit
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
- _iswdigit_l
- _isdigit_l
- iswdigit
- isdigit
- _istdigit
- _istdigit_l
dev_langs:
- C++
helpviewer_keywords:
- iswdigit function
- iswdigit_l function
- _iswdigit_l function
- _istdigit_l function
- _istdigit function
- istdigit function
- isdigit function
- isdigit_l function
- _ismbcdigit_l function
- _isdigit_l function
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f51d402080790917dda16d115e5dd19c5b8256bd
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="isdigit-iswdigit-isdigitl-iswdigitl"></a>isdigit, iswdigit, _isdigit_l, _iswdigit_l

정수가 10진수 문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int isdigit(
   int c
);
int iswdigit(
   wint_t c
);
int _isdigit_l(
   int c,
   _locale_t locale
);
int _iswdigit_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

각각의 이러한 루틴이 0이 아닌 경우 반환 *c* 10 진수가 문자의 특정 표현입니다. **isdigit** 경우 0이 아닌 값을 반환 *c* 는 10 진수 숫자 (0-9). **iswdigit** 경우 0이 아닌 값을 반환 *c* 10 진수가 문자에 해당 하는 와이드 문자입니다. 이러한 각 루틴 0을 반환 *c* 테스트 조건을 만족 하지 않습니다.

이 있는 이러한 함수 버전은 **_l** 접미사는 로캘 종속 동작에 현재 로캘 대신 전달 된 로캘을 사용 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

동작은 **isdigit** 및 **_isdigit_l** 경우 정의 되지 않습니다 *c* 가 EOF가 또는 0-0xFF 까지의 범위에 있습니다. CRT 디버그 라이브러리 사용 되는 경우 및 *c* 함수 생성에서는 이러한 값 중 하나가 아닙니다 한 어설션입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istdigit**|**isdigit**|[_ismbcdigit](ismbcalnum-functions.md)|**iswdigit**|
|**_istdigit_l**|**_isdigit_l**|[_ismbcdigit_l](ismbcalnum-functions.md)|**_iswdigit_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**isdigit**|\<ctype.h>|
|**iswdigit**|\<ctype.h> 또는 \<wchar.h>|
|**_isdigit_l**|\<ctype.h>|
|**_iswdigit_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
