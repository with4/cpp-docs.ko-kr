---
title: "_create_locale, _wcreate_locale | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_create_locale"
  - "__create_locale"
  - "_wcreate_locale"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "create_locale"
  - "_create_locale"
  - "__create_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__create_locale 함수"
  - "_create_locale 함수"
  - "create_locale 함수"
  - "로캘, 만들기"
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _create_locale, _wcreate_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 개체를 만듭니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `category`  
 카테고리입니다.  
  
 `locale`  
 로캘 지정자입니다.  
  
## 반환 값  
 유효한 `locale` 과 `category` 가 지정된 경우, `_locale_t` 개체 같은 지정된 로캘 설정을 반환합니다.  프로그램의 현재 로캘 설정은 변하지 않습니다.  
  
## 설명  
 `_create_locale` 함수는 많은 CRT 함수\( `_l` 접미사를 사용하는 함수\) 의 로캘 고유의 버전을 위해 특정 국가별 설정을 나타내는 개체를 만들 수 있도록 합니다.  동작은 지정된 로캘 설정에 현재 환경을 적용하는 대신 반환된 `_locale_t` 에 설정이 저장되는 것을 제외하고 `setlocale` 와 유사합니다.   `_locale_t` 구조체는 더이상 필요가 업을때 [\_free\_locale](../../c-runtime-library/reference/free-locale.md) 를 사용하여 해재되어야 합니다.  
  
 `_wcreate_locale`는 `_create_locale`의 와이드 문자 버전이며, `_wcreate_locale`의 `locale` 인수는 와이드 문자 문자열입니다.  그렇지 않으면 `_wcreate_locale` 와 `_create_locale` 는 동일하게 작동합니다.  
  
 `category` 인수는 영향을 받는 로캘 고유의 작동의 부분을 지정합니다.  플래그는 `category` 를 위해 사용하고 영향을 받는 프로그램의 부분이 다음 표에 나와 있습니다.  
  
 `LC_ALL`  
 아래에 나열된 모든 범주입니다.  
  
 `LC_COLLATE`  
 `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll`, 및 `wcsxfrm` 함수입니다.  
  
 `LC_CTYPE`  
 문자 처리 함수입니다. \(영향을 받지 않는 `isdigit`, `isxdigit`, `mbstowcs`, 및 `mbtowc` 는 제외합니다.\)  
  
 `LC_MONETARY`  
 Monetary 서식 정보는 `localeconv` 함수에 의해 반환합니다.  
  
 `LC_NUMERIC`  
 형식이 지정 된 출력 루틴\( `printf`과 같은\), 데이터 변환 루틴, `localeconv` 에 의해 반환된 비통화 서식 정보에 대한 10진 소수점 문자입니다.  10진 소수점 문자 이외에도 `LC_NUMERIC` 는 1000단위 구분 기호와 [localeconv](../../c-runtime-library/reference/localeconv.md)에 의해 반환된 그룹화 컨트롤 문자열을 설정합니다.  
  
 `LC_TIME`  
 `strftime` 및 `wcsftime` 함수입니다.  
  
 이 함수는 `category` 와 `locale` 매개 변수의 유효성을 검사합니다.  범주 매개 변수가 이전 테이블에 지정 된 값 중 하나가 아니거나 `locale` 가 `NULL` 인경우 이 함수는 `NULL` 을 반환합니다.  
  
 `locale` 인수는 로캘을 지정하는 문자열에 대한 포인터 입니다.  `locale` 인수의 형식에 대한 자세한 정보는 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) 를 참조하십시오.  
  
 `locale` 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가\/지역 코드, 코드 페이지 또는 한 언어 문자열, 국가\/지역 코드 및 코드 페이지를 사용할 수 있습니다.  사용 가능한 로캘 이름, 언어, 국가\/지역 코드 및 코드 페이지의 집합은 문자 당 2 바이트 이상을 필요로 하는 코드 페이지를 제외하고 Windows NLS API에서 모두 지원됩니다.\-예를들어 UTF\-7 and UTF\-8.  UTF\-7 또는 UTF\-8와 같은 코드 페이지를 제공 하는 경우 `_create_locale` 는 실패하고 NULL을 반환 합니다.  `_create_locale` 에 의해 지원되는 로캘 이름의 집합은 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) 에 설명되어 있습니다.  `_create_locale` 에 의해 지원되는 언어 및 국가\/지역 문자열의 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) and [국가\/지역 문자열](../../c-runtime-library/country-region-strings.md) 에 나열되어 있습니다.  
  
 로캘 설정에 대한 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 를 참조하십시오.  
  
 이 함수의 이전 이름인 `__create_locale` \(두 개의 선행 밑줄\)은 포함 되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_create_locale`|\<locale.h\>|  
|`_wcreate_locale`|\<locale.h\> 또는 \<wchar.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
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
       //  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In de-CH locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
  
       // Create a locale object representing the default C locale  
       locale = _create_locale(LC_ALL, "C");  
       time (&ltime);  
       _gmtime64_s(&thetime, &ltime);  
  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In 'C' locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
}  
```  
  
## 샘플 출력  
  
```  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## 해당 .NET Framework 항목  
 [System::Globalization::CultureInfo Class](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)  
  
## 참고 항목  
 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [언어 문자열](../../c-runtime-library/language-strings.md)   
 [국가\/지역 문자열](../../c-runtime-library/country-region-strings.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)   
 [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)