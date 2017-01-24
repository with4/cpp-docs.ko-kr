---
title: "_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l | Microsoft Docs"
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
  - "_mbsicoll_l"
  - "_stricoll_l"
  - "_mbsicoll"
  - "_wcsicoll_l"
  - "_wcsicoll"
  - "_stricoll"
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
  - "stricoll"
  - "_stricoll"
  - "_wcsicoll"
  - "mbsicoll_l"
  - "_mbsicoll"
  - "_ftcsicoll"
  - "wcsicoll_l"
  - "_tcsicoll"
  - "mbsicoll"
  - "stricoll_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsicoll 함수"
  - "_mbsicoll 함수"
  - "_mbsicoll_l 함수"
  - "_stricoll 함수"
  - "_stricoll_l 함수"
  - "_tcsicoll 함수"
  - "_wcsicoll 함수"
  - "코드 페이지, 문자열 비교에 사용"
  - "ftcsicoll 함수"
  - "mbsicoll 함수"
  - "mbsicoll_l 함수"
  - "stricoll 함수"
  - "stricoll_l 함수"
  - "문자열 비교[C++], 문화권별"
  - "문자열[C++], 코드 페이지로 비교"
  - "tcsicoll 함수"
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 관련 정보를 사용하여 문자열을 비교합니다.  
  
> [!IMPORTANT]
>  `_mbsicoll` 와 `_mbsicoll_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _stricoll(  
   const char *string1,  
   const char *string2   
);  
int _wcsicoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `string1, string2`  
 비교할 Null 종료 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 각 이러한 함수들은 다음과 같이 `string2`*,* 로 `string1` 의 관계가 나태나는 값을 반환합니다.  
  
|반환 값|문자열 1과 문자열 2의 관계|  
|----------|----------------------|  
|\< 0|`string1` \< `string2`|  
|0|`string1` \= `string2`|  
|\> 0|`string1` \> `string2`|  
|`_NLSCMPERROR`|오류가 발생했습니다.|  
  
 이러한 각 함수를 `_NLSCMPERROR` 를 반환합니다.  이 `_NLSCMPERROR` 을 사용하면, 이 `STRING.H` 혹은 `MBSTRING.H` 어느쪽 역시 포함합니다.  `_wcsicoll` 은 `string1` 혹은 `string2` 어느쪽은 대조하는 시퀀스의 도메인 외부의 와이드 문자 코드를 포함합니다.  오류가 발생하면, `_wcsicoll` 은 `errno` 을 `EINVAL` 으로 설정할 수 있습니다.  이 `_wcsicoll` 의 호출에서 오류를 확인하려면, `_wcsicoll` 을 호출한 후 `errno` 을 검사하고 `errno` 로 설정합니다.  
  
## 설명  
 각 함수는 `string1` 대\/소문자 구분 비교와 현재 사용중인 코드 페이지에 따라 `string2` 으로 수행합니다.  문자 사이는 차이점이 현재 코드 페이지에 순서와 lexicographic 문자 순서 설정 및 문자열 비교에 대한 관심의 차이가 있는 경우에 이러한 함수를 사용해야 합니다.  
  
 `_stricmp` 은, `_stricoll` 비교는 로캘의 `LC_CTYPE` 와 `LC_COLLATE` 범주들을 따르는데에 비해서, `_stricmp` 비교는 `LC_CTYPE` 로 영향을 받은 `_stricoll` 과는 다릅니다.  이 `LC_COLLATE` 범주의 더 많은 정보를 보려면, [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 와 [Locale Categories](../../c-runtime-library/locale-categories.md)을 보세요.  `_l` 접미사가 없는 이러한 함수의 버전은 현재 로캘을 사용합니다; `_l` 접미사가 있는 버전은 대신 전달된 로캘을 사용한다는 것을 제외하고는 같습니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  만약 `string1` 혹은 `string2` 이 `NULL` 포인터인 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명된것으로서 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsicoll`|`_stricoll`|`_mbsicoll`|`_wcsicoll`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_stricoll`, `_stricoll_l`|\<string.h\>|  
|`_wcsicoll`, `_wcsicoll_l`|\<wchar.h\>, \<string.h\>|  
|`_mbsicoll`, `_mbsicoll_l`|\<mbstring.h\>|  
  
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