---
title: "_create_locale, _wcreate_locale | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 73e89121dda53300b276b76f49625ad274df4519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale
로캘 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
_locale_t _create_locale(  
   int category,  
   const char *locale   
);  
_locale_t _wcreate_locale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `category`  
 범주입니다.  
  
 `locale`  
 로캘 지정자입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 `locale` 및 `category`를 지정한 경우 지정된 로캘 설정을 `_locale_t` 개체로 반환합니다. 프로그램의 현재 로캘 설정은 변경되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `_create_locale` 함수를 사용하면 로캘별 버전의 여러 CRT 함수(`_l` 접미사가 있는 함수)에서 사용하기 위한 특정 지역별 설정을 나타내는 개체를 만들 수 있습니다. 지정된 로캘 설정을 현재 환경에 적용하는 대신, 반환되는 `_locale_t` 구조체에 설정을 저장한다는 점을 제외하면 동작이 `setlocale`과 유사합니다. `_locale_t` 구조체가 더 이상 필요 없는 경우 [_free_locale](../../c-runtime-library/reference/free-locale.md)을 사용하여 해제해야 합니다.  
  
 `_wcreate_locale`은 `_create_locale`의 와이드 문자 버전이며, `locale`에 대한 `_wcreate_locale` 인수는 와이드 문자열입니다. 그렇지 않으면 `_wcreate_locale`과 `_create_locale`이 동일하게 작동합니다.  
  
 `category` 인수는 영향을 받는 로캘별 동작의 일부를 지정합니다. `category`에 사용된 플래그 및 영향을 받는 프로그램의 일부가 다음 표에 나와 있습니다.  
  
 `LC_ALL`  
 아래에 나열된 모든 범주입니다.  
  
 `LC_COLLATE`  
 `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` 및 `wcsxfrm` 함수입니다.  
  
 `LC_CTYPE`  
 문자 처리 함수(영향을 받지 않는 `isdigit`, `isxdigit`, `mbstowcs` 및 `mbtowc` 제외)입니다.  
  
 `LC_MONETARY`  
 `localeconv` 함수에 의해 반환되는 통화 서식 정보입니다.  
  
 `LC_NUMERIC`  
 서식이 지정된 출력 루틴(예: `printf`), 데이터 변환 루틴 및 `localeconv`에 의해 반환된 비통화 서식 정보에 대한 소수점 문자입니다. 소수점 문자 이외에도 `LC_NUMERIC`은 1,000단위 구분 기호와 [localeconv](../../c-runtime-library/reference/localeconv.md)에 의해 반환된 그룹화 제어 문자열을 설정합니다.  
  
 `LC_TIME`  
 `strftime` 및 `wcsftime` 함수입니다.  
  
 이 함수는 `category` 및 `locale` 매개 변수의 유효성을 검사합니다. category 매개 변수가 이전 표에 지정된 값 중 하나가 아닌 경우 또는 `locale`이 `NULL`인 경우 함수가 `NULL`을 반환합니다.  
  
 `locale` 인수는 로캘을 지정하는 문자열에 대한 포인터입니다. `locale` 인수의 형식에 대한 자세한 내용은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)을 참조하세요.  
  
 `locale` 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지, 언어 문자열, 국가/지역 코드 및 코드 페이지를 가져올 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지의 집합에는 문자당 3바이트 이상이 필요한 코드 페이지(예: UTF-7 및 UTF-8)를 제외하고, Windows NLS API에서 지원하는 모든 항목이 포함됩니다. UTF-7 또는 UTF-8과 같은 코드 페이지를 제공하는 경우 `_create_locale`이 실패하고 NULL이 반환됩니다. `_create_locale`에서 지원하는 로캘 이름 집합은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)에 설명되어 있습니다. `_create_locale`에서 지원하는 언어 및 국가/지역 문자열 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)에 나열되어 있습니다.  
  
 로캘 설정에 대한 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  
  
 이 함수의 이전 이름인 `__create_locale`(앞에 밑줄 두 개 포함)은 더 이상 사용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h>|  
|`_wcreate_locale`|\<locale.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [언어 문자열](../../c-runtime-library/language-strings.md)   
 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)