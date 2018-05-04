---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs:
- C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e399cb38fee83fee23f88732bb2186c4b501c152
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l
문자를 소문자로 변환합니다.

## <a name="syntax"></a>구문

```C
int tolower(
   int c
);
int _tolower(
   int c
);
int towlower(
   wint_t c
);
int _tolower_l(
   int c,
   _locale_t locale
);
int _towlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
변환할 문자입니다.

*locale*<br/>
로캘별 변환에 사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 각 루틴의 복사본을 변환 *c* 를 소문자로 변환 하 여 가능 하 고 결과 반환 하는 경우. 오류를 나타내기 위해 예약된 반환 값은 없습니다.

## <a name="remarks"></a>설명

이러한 각 루틴은 가능하며 관련성이 있는 경우 지정된 대문자를 소문자로 변환합니다. 대/소문자 변환은 **towlower** 는 로캘에 따라 다릅니다. 현재 로캘에서 유효한 문자의 대/소문자만 변경됩니다. 없이 함수는 **_l** 접미사를 사용 하 여 현재 설정 로캘 합니다. 있는 이러한 함수 버전은 **_l** 접미사 로캘을 매개 변수로 하 고 현재 설정 하는 대신 사용 하는 로캘 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

에 대 한 순서 대로 **_tolower** 예상된 결과를 제공할 [__isascii](isascii-isascii-iswascii.md) 및 [isupper](isupper-isupper-l-iswupper-iswupper-l.md) 모두 반환 해야 0이 아닌 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**tolower**|**_mbctolower**|**towlower**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** 및 **_towlower_l** 로캘에 종속 되지 않습니다 있고 직접 호출할 수 있는 것은 아닙니다. 내부 사용을 위해 제공 되는 **_totlower_l**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**tolower**|\<ctype.h>|
|**_tolower**|\<ctype.h>|
|**towlower**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[to 함수](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[to 함수](../../c-runtime-library/to-functions.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
