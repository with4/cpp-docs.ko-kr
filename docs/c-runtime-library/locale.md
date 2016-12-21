---
title: "로캘 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "국가 정보"
  - "언어 정보 루틴"
  - "로캘 루틴"
  - "지역화, 로캘"
  - "setlocale 함수"
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 로캘
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*로캘* 은 프로그램을 사용자 지정 하는 데 사용할 수 있는 국가\/지역 및 언어 설정을 참조 합니다.  일부 로캘\-종속 범주는 날짜 및 통화 값의 형식 표시를 포함합니다.  자세한 내용은 [로캘 범주](../c-runtime-library/locale-categories.md)을 참조하십시오.  
  
 다음 `_l` 접미사 없이 함수를 사용하는 동안 스레드의 로캘 정보 또는 현재 프로그램의 일부 또는 모두를 바꾸거나 쿼리하는 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 함수를 사용하십시오.  다음 `_l` 접미사를 사용하는 함수는 해당 특정 함수가 실행되는 동안 로캘 정보를 전달하는 로캘 매개 변수를 사용합니다.  다음 `_l` 접미사를 사용하는 함수를 사용하는 로캘을 만들기 위해 [\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)을 사용합니다.  다음 [\_free\_locale](../c-runtime-library/reference/free-locale.md)를 사용하여 로캘을 자유롭게 합니다.  현재 로캘을 가져오려면 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)를 사용하십시오.  
  
 각 스레드가 로캘 또는 프로그램의 모든 스레드가 동일한 로캘을 공유하는지 제어하기 위해 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 을 사용합니다.  자세한 내용은 [로캘 및 코드 페이지](../text/locales-and-code-pages.md)를 참조하십시오.  
  
 다음 `_s` 접미사 \("안전"\)에 의해 다음 표의 보다 안전한 버전의 함수가 표시될 수 있습니다.  자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)을 참조하십시오.  
  
### 로캘 종속 루틴  
  
|루틴|기능|`setlocale` 범주 설정 종속성|  
|--------|--------|---------------------------|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|문자를 부동 소수점 값으로 변환합니다.|`LC_NUMERIC`|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|문자를 정수 값으로 변환합니다.|`LC_NUMERIC`|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|문자를 64\-비트 정수 값으로 변환합니다.|`LC_NUMERIC`|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|문자를 long 값으로 변환합니다.|`LC_NUMERIC`|  
|[\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|문자를 long double 값으로 변환합니다.|`LC_NUMERIC`|  
|[is Routines](../c-runtime-library/is-isw-routines.md)|특정 조건에 대한 지정된 정수를 테스트합니다.|`LC_CTYPE`|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|선행 바이트에 대한 테스트를 합니다.|`LC_CTYPE`|  
|[localeconv](../c-runtime-library/reference/localeconv.md)|수량 숫자 서식에 대한 적절한 값을 읽습니다.|`LC_MONETARY, LC_NUMERIC`|  
|[MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)|현재 로컬\(STDLIB.H에 정의된 매크로\)내의 모든 멀티 바이트 문자의 최대 길이 \(바이트\) 입니다.|`LC_CTYPE`|  
|[\_mbccpy, \_mbccpy\_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|한 멀티 바이트 문자를 복사합니다.|`LC_CTYPE`|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|멀티 바이트 문자의 바이트의 수를 반환하고 유효성 검사를 합니다.|`LC_CTYPE`|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|멀티 바이트\-문자 문자열: 문자열의 각 문자를 검사합니다.; 문자열의 길이를 반환합니다.|`LC_CTYPE`|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|멀티 바이트의 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다.|`LC_CTYPE`|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|멀티 바이트 문자를 해당 와이드 문자로 변환합니다.|`LC_CTYPE`|  
|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 함수|형식이 지정된 출력을 씁니다.|`LC_NUMERIC` \(기수 문자 출력을 결정합니다.\)|  
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 함수|포맷된 입력을 읽습니다.|`LC_NUMERIC`\(기수 문자 인식 여부 결정\)|  
|[setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|프로그램에 대한 로캘을 선택합니다.|해당 없음|  
|[strcoll, wcscoll, \_mbscoll, \_strcoll\_l, \_wcscoll\_l, \_mbscoll\_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|두 문자열의 문자 비교|`LC_COLLATE`|  
|[\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|대\/소문자에 상관없이 두 문자열을 비교|`LC_CTYPE`|  
|[\_stricoll, \_wcsicoll, \_mbsicoll, \_stricoll\_l, \_wcsicoll\_l, \_mbsicoll\_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|\(인식하지 않는 경우\) 두 문자열의 문자들을 비교합니다.|`LC_COLLATE`|  
|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|두 문자열의 첫 `n` 문자를 비교합니다.|`LC_COLLATE`|  
|[\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|경우에 상관 없이 두 문자열을 비교합니다.|`LC_CTYPE`|  
|[\_strnicoll, \_wcsnicoll, \_mbsnicoll, \_strnicoll\_l, \_wcsnicoll\_l, \_mbsnicoll\_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|\(인식하지 않는 경우\) 두 문자열의 첫 `n` 문자들을 비교합니다.|`LC_COLLATE`|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|제공된 `format` 인수에 따른 날짜 및 시간 값의 형식입니다.|`LC_TIME`|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|제자리에서, 각각 대문자를 제공된 소문자로 변환합니다.|`LC_CTYPE`|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|문자열을 `double` 값으로 변환합니다.|`LC_NUMERIC`\(기수 문자 인식 여부 결정\)|  
|[strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|문자열을 `long`값으로 변환합니다.|`LC_NUMERIC`\(기수 문자 인식 여부 결정\)|  
|[strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|문자열을 부호 없는 long 형식의 값으로 변환합니다.|`LC_NUMERIC`\(기수 문자 인식 여부 결정\)|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|제자리에서, 각각 소문자를 대문자로 변환합니다.|`LC_CTYPE`|  
|[strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|문자열을 로캘에 따른 수집된 형식으로 변환합니다.|`LC_COLLATE`|  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|해당 문자를 소문자로 변환합니다.|`LC_CTYPE`|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|해당 문자를 대문자로 변환합니다.|`LC_CTYPE`|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|해당 멀티 바이트 문자의 시퀀스로 와이드 문자의 시퀀스를 변환합니다.|`LC_CTYPE`|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|와이드 바이트 문자를 해당 멀티바이트 문자로 변환합니다.|`LC_CTYPE`|  
  
> [!NOTE]
>  멀티 바이트 루틴에 대해, 멀티 바이트 코드 페이지는 [\>setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)로 설정된 로캘과 동일해야 합니다.  [\_setmbcp](../c-runtime-library/reference/setmbcp.md), `_MB_CP_LOCALE` 의 인수를 사용하여 `setlocale` 코드 페이지와 같은 멀티 바이트 코드 페이지를 만듭니다.  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)