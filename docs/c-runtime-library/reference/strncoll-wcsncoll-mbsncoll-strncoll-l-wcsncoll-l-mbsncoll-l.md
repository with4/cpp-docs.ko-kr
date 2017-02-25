---
title: "_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strncoll"
  - "_mbsncoll_l"
  - "_wcsncoll"
  - "_wcsncoll_l"
  - "_mbsncoll"
  - "_strncoll_l"
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
  - "mbsncoll_l"
  - "strncoll"
  - "_wcsncoll"
  - "_tcsnccoll"
  - "_ftcsnccoll"
  - "wcsncoll"
  - "_mbsncoll"
  - "wcsncoll_l"
  - "strncoll_l"
  - "_ftcsncoll"
  - "_strncoll"
  - "_tcsncoll"
  - "mbsncoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccoll 함수"
  - "_ftcsncoll 함수"
  - "_mbsncoll 함수"
  - "_mbsncoll_l 함수"
  - "_strncoll 함수"
  - "_strncoll_l 함수"
  - "_tcsnccoll 함수"
  - "_tcsncoll 함수"
  - "_wcsncoll 함수"
  - "_wcsncoll_l 함수"
  - "코드 페이지, 문자열 비교에 사용"
  - "ftcsnccoll 함수"
  - "ftcsncoll 함수"
  - "mbsncoll 함수"
  - "mbsncoll_l 함수"
  - "문자열[C++], 코드 페이지로 비교"
  - "strncoll 함수"
  - "strncoll_l 함수"
  - "tcsnccoll 함수"
  - "tcsncoll 함수"
  - "wcsncoll 함수"
  - "wcsncoll_l 함수"
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘별 정보를 사용하여 문자열을 비교합니다.  
  
> [!IMPORTANT]
>  `_mbsncoll` 및 `_mbsncoll_l`은 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
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
 비교할 문자 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 함수는 다음과 같이 `string1` 및 `string2`의 부분 문자열 간 관계를 나타내는 값을 반환합니다.  
  
|반환 값|문자열 1과 문자열 2의 관계|  
|----------|----------------------|  
|\< 0|`string1`가 `string2`보다 작은 경우|  
|0|`string1`이 `string2`와 같은 경우|  
|\> 0|`string1`가 `string2`보다 큰 경우|  
  
 이러한 각 함수는 `_NLSCMPERROR`를 반환합니다.  `_NLSCMPERROR`를 사용하려면 STRING.h 또는 MBSTRING.h를 포함합니다.  `_wcsncoll` 또는 `string1`에 정렬 순서 도메인을 벗어나는 와이드 문자 코드가 포함된 경우 `string2`이 실패할 수 있습니다.  오류가 발생하면 `_wcsncoll`에서 `errno`를 `EINVAL`로 설정할 수 있습니다.  `_wcsncoll`에 대한 호출 시 오류가 있는지 확인하려면 `errno`를 0으로 설정한 다음 `errno` 호출 후 `_wcsncoll`를 검사합니다.  
  
## 설명  
 이러한 각 함수는 현재 사용 중인 코드 페이지에 따라 `count` 및 `string1`에 있는 첫 번째 `string2` 문자를 대\/소문자를 구분하며 비교합니다.  코드 페이지에서 문자 집합 순서와 사전적 문자 순서가 다르며 이러한 차이가 문자열 비교 시 중요한 경우에만 이러한 함수를 사용하세요.  문자 집합 순서는 로캘별로 다릅니다.  `_l` 접미사가 없는 이러한 함수의 버전은 현재 로캘을 사용하지만 `_l` 접미사가 있는 버전은 전달되는 로캘을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  `string1` 또는 `string2`가 null 포인터이거나 `count`가 `INT_MAX`보다 큰 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[\_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strncoll`, `_strncoll_l`|\<string.h\>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h\> 또는 \<string.h\>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
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