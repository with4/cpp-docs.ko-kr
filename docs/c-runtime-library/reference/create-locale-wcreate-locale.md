---
title: _create_locale, _wcreate_locale | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9be41a2d156a522c74349c3457295502ae6d4f43
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451942"
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale

로캘 개체를 만듭니다.

## <a name="syntax"></a>구문

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>매개 변수

*category*<br/>
범주입니다.

*locale*<br/>
로캘 지정자입니다.

## <a name="return-value"></a>반환 값

유효한 경우 *로캘* 및 *범주* 증명이로 지정 된 로캘 설정을 반환는 **_locale_t** 개체입니다. 프로그램의 현재 로캘 설정은 변경되지 않습니다.

## <a name="remarks"></a>설명

**_create_locale** 함수 로캘 특정 버전의 많은 CRT 함수에서 사용 하기 위해 특정 국가별 설정을 나타내는 개체를 만들 수 있습니다 (함수는 **_l** 접미사 ). 동작은 유사 **setlocale**단 설정은 현재 환경에 지정 된 로캘 설정을 적용 하는 대신에 저장 되며, 한 **_locale_t** 반환 되는 구조입니다. **_locale_t** 구조를 사용 하 여 해제 해야 [_free_locale](free-locale.md) 더 이상 필요 없는 경우.

**_wcreate_locale** 의 와이드 문자 버전이 **_create_locale**; *로캘* 인수를 **_wcreate_locale** 는 와이드 문자 문자열입니다. **_wcreate_locale** 및 **_create_locale** 동일 하 게 작동 합니다.

*범주* 인수는 영향을 로캘 관련 동작의 일부를 지정 합니다. 에 사용 되는 플래그 *범주* 및에 영향을 주는지 프로그램의 일부는 다음 표에 나와 있는 것 처럼 합니다.

|*범주* 플래그|미치는 영향|
|-|-|
**LC_ALL**|아래에 나열된 모든 범주입니다.
**LC_COLLATE**|**strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_ strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, 및 **wcsxfrm** 함수입니다.
**LC_CTYPE**|문자 처리 함수 (제외 하 고 **isdigit**, **isxdigit**, **mbstowcs**, 및 **mbtowc**, 영향을 받지 않습니다).
**LC_MONETARY**|반환 되는 통화 서식 정보는 **localeconv** 함수입니다.
**LC_NUMERIC**|소수점 형식이 지정 된 출력 루틴에 대 한 문자 (예: **printf**), 데이터 변환 루틴 및에서 반환 된 비 통화 서식 지정 정보에 대 한 **localeconv**합니다. 소수점 문자 이외에 **LC_NUMERIC** 집합 1000 단위 구분 기호 및 그룹화 제어 문자열에서 반환 된 [localeconv](localeconv.md)합니다.
**LC_TIME**|**strftime** 및 **wcsftime** 함수입니다.

이 함수 유효성을 검사는 *범주* 및 *로캘* 매개 변수입니다. 경우에 category 매개 변수 앞의 표에 지정 된 값 중 하나가 아닌 경우 또는 *로캘* 은 **NULL**, 함수 반환 **NULL**합니다.

*로캘* 인수는 로캘을 지정 하는 문자열에 대 한 포인터입니다. 형식에 대 한 내용은 *로캘* 인수 참조 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)합니다.

*로캘* 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지 또는 언어 문자열, 국가/지역 코드 및 코드 페이지를 사용할 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지의 집합에는 문자당 3바이트 이상이 필요한 코드 페이지(예: UTF-7 및 UTF-8)를 제외하고, Windows NLS API에서 지원하는 모든 항목이 포함됩니다. Utf-7 또는 u t F-8과 같은 코드 페이지를 제공 하는 경우 **_create_locale** 실패 하 고 반환 됩니다 **NULL**합니다. 지원 되는 로캘 이름 집합 **_create_locale** 에 설명 된 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)합니다. 지 원하는 언어 및 국가/지역 문자열 집합이 **_create_locale** 에 나열 된 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)합니다.

로캘 설정에 대한 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하세요.

이 함수의 이전 이름인 **__create_locale** (두 개의 선행 밑줄 포함), 사용 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>참고자료

[로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[언어 문자열](../../c-runtime-library/language-strings.md)<br/>
[국가/지역 문자열](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
