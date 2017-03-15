---
title: "_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnicoll_l"
  - "_mbsnicoll"
  - "_wcsnicoll_l"
  - "_strnicoll"
  - "_strnicoll_l"
  - "_wcsnicoll"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcshicoll_l"
  - "_ftcsncicoll"
  - "strnicoll_l"
  - "_wcsnicoll"
  - "mbsnicoll_l"
  - "_strnicoll"
  - "mbsnicoll"
  - "_ftcsnicoll"
  - "wcsnicoll"
  - "_tcsnicoll"
  - "_mbsnicoll"
  - "strinicoll"
  - "_tcsncicoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsncicoll 함수"
  - "_ftcsnicoll 함수"
  - "_mbsnicoll 함수"
  - "_mbsnicoll_l 함수"
  - "_strnicoll 함수"
  - "_strnicoll_l 함수"
  - "_tcsncicoll 함수"
  - "_tcsnicoll 함수"
  - "_wcsnicoll 함수"
  - "_wcsnicoll_l 함수"
  - "코드 페이지, 문자열 비교에 사용"
  - "ftcsncicoll 함수"
  - "ftcsnicoll 함수"
  - "mbsnicoll 함수"
  - "mbsnicoll_l 함수"
  - "문자열[C++], 코드 페이지로 비교"
  - "strnicoll 함수"
  - "strnicoll_l 함수"
  - "tcsncicoll 함수"
  - "tcsnicoll 함수"
  - "wcsnicoll 함수"
  - "wcsnicoll_l 함수"
ms.assetid: abf0c569-725b-428d-9ff2-924f430104b4
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 관련 정보를 사용하여 문자열을 비교합니다.  
  
> [!IMPORTANT]
>  `_mbsnicoll` 와 `_mbsnicoll_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _strnicoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicoll(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count   
);  
int _mbsnicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2 ,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `string1, string2`  
 비교할 Null 종료 문자열입니다.  
  
 `count`  
 비교할 문자 수.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 함수들은 `string1` 과 `string2`*,* 으로 따르는 문자열의 관계를 나타내는 값을 반환합니다.  
  
|반환 값|문자열 1과 문자열 2의 관계|  
|----------|----------------------|  
|\< 0|`string1` \< `string2`|  
|0|`string1` \= `string2`|  
|\> 0|`string1` \> `string2`|  
  
 이러한 각 함수를 `_NLSCMPERROR` 를 반환합니다.  이 `_NLSCMPERROR`를 사용하여, STRING.H 혹은 MBSTRING.H 어느 쪽을 포함합니다.  `_wcsnicoll` 은 `string1` 혹은 `string2` 어느쪽은 대조하는 시퀀스의 도메인 외부의 와이드 문자 코드를 포함합니다.  오류가 발생하면, `_wcsnicoll` 은 `errno` 을 `EINVAL` 으로 설정할 수 있습니다.  이 `_wcsnicoll` 의 호출에서 오류를 확인하려면, `_wcsnicoll`**.** 을 호출한 후 `errno` 을 검사하고 `errno` 로 설정합니다.  
  
## 설명  
 이러한 함수들은 코드 페이지에 따라 `string1` 과 `string2` 인 첫 `count` 문자의 대\/소문자 구분 비교를 수행합니다.  문자 사이는 차이점이 코드 페이지에 순서와 lexicographic 문자 순서 설정 및 문자열 비교에 대한 관심의 차이가 있는 경우에 이러한 함수를 사용해야 합니다.  이 `_l` 이 없는 이러한 함수들의 버전은 현재 로캘 및 코드 페이지를 사용 하는 접미사입니다.  이`_l` 접미사를 사용하여 버전에 전달 된 로케일을 사용 한다는 점을 제외 하면 동일 합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  하나 `string1` 또는 `string2` 는 널 포인터 경우, 또는 숫자보다 큰 `INT_MAX`, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명된데로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR` 를 반환하고 `errno` 를 `EINVAL`**.** 로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncicoll`|`_strnicoll`|`_mbsnbicoll`|`_wcsnicoll`|  
|`_tcsnicoll`|`_strnicoll`|[\_mbsnbicoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsnicoll`|  
|`_tcsnicoll_l`|`_strnicoll_l`|`_mbsnbicoll_l`|`_wcsnicoll_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strnicoll`, `_strnicoll_l`|\<string.h\>|  
|`_wcsnicoll`, `_wcsnicoll_l`|\<wchar.h\> 또는 \<string.h\>|  
|`_mbsnicoll`, `_mbsnicoll_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)