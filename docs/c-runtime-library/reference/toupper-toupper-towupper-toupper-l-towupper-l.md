---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
dev_langs:
- C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e5ee092690f257950acd84e1af69ca4c4f3e4c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

문자를 대문자로 변환합니다.

## <a name="syntax"></a>구문

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
변환할 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 각 루틴의 복사본을 변환 *c*, 가능한 경우 결과 반환 합니다.

경우 *c* 는 와이드 문자를 **iswlower** 0을 해당 와이드 문자 이며 [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) 이 값은 0 **towupper** 해당 와이드 문자를 반환 합니다. 그렇지 않으면 **towupper** 반환 *c* 변경 되지 않습니다.

오류를 나타내기 위해 예약된 반환 값은 없습니다.

에 대 한 순서 대로 **toupper** 예상된 결과를 제공할 [__isascii](isascii-isascii-iswascii.md) 및 [islower](islower-iswlower-islower-l-iswlower-l.md) 모두 반환 해야 0이 아닌 합니다.

## <a name="remarks"></a>설명

이러한 각 루틴은 가능하며 적절한 경우 지정된 소문자를 대문자로 변환합니다. 대/소문자 변환은 **towupper** 는 로캘에 따라 다릅니다. 현재 로캘에서 유효한 문자의 대/소문자만 변경됩니다. 없이 함수는 **_l** 접미사를 사용 하 여 현재 설정 로캘 합니다. 있는 이러한 함수 버전은 **_l** 접미사 로캘을 매개 변수로 하 고 현재 설정 하는 대신 사용 하는 로캘 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

에 대 한 순서 대로 **toupper** 예상된 결과를 제공할 [__isascii](isascii-isascii-iswascii.md) 및 [isupper](isupper-isupper-l-iswupper-iswupper-l.md) 모두 반환 해야 0이 아닌 합니다.

[데이터 변환 루틴](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** 및 **_towupper_l** 로캘에 종속 되지 않습니다 있고 직접 호출할 수 있는 것은 아닙니다. 내부 사용을 위해 제공 되는 **_totupper_l**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[to 함수](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[to 함수](../../c-runtime-library/to-functions.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
