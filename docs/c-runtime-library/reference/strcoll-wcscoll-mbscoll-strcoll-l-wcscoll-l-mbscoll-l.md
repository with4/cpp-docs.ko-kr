---
title: "strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscoll"
  - "_mbscoll"
  - "_mbscoll_l"
  - "strcoll"
  - "_strcoll_l"
  - "_wcscoll_l"
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
  - "wcscoll"
  - "_mbscoll"
  - "_tcscoll"
  - "_ftcscoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "코드 페이지, 문자열 비교에 사용"
  - "mbscoll 함수"
  - "wcscoll_l 함수"
  - "ftcscoll 함수"
  - "wcscoll 함수"
  - "_strcoll_l 함수"
  - "tcscoll 함수"
  - "_ftcscoll 함수"
  - "_tcscoll 함수"
  - "_wcscoll_l 함수"
  - "_mbscoll 함수"
  - "strcoll_l 함수"
  - "strcoll 함수"
  - "문자열[C++], 코드 페이지로 비교"
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘 또는 지정한 LC\_COLLATE 변환 상태 범주를 사용하여 문자열을 비교합니다.  
  
> [!IMPORTANT]
>  `_mbscoll` 와 `_mbscoll_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### 매개 변수  
 `string1`, `string2`  
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
  
 이러한 각 함수는 오류의 `_NLSCMPERROR` 를 반환합니다.  이 `_NLSCMPERROR`를 사용하여, STRING.H 혹은 MBSTRING.H 어느 쪽을 포함합니다.  `wcscoll` 은 `string1` 혹은 `string2` 이 NULL 이거나 어느쪽은 대조하는 시퀀스의 도메인 외부의 와이드 문자 코드를 포함합니다.  오류가 발생하면, `wcscoll` 은 `errno` 을 `EINVAL` 으로 설정할 수 있습니다.  이 `wcscoll` 의 호출에서 오류를 확인하려면, `wcscoll` 을 호출한 후 `errno` 을 검사하고 `errno` 로 설정합니다.  
  
## 설명  
 각 함수는 `string1` 대\/소문자 구분 비교와 현재 사용중인 코드 페이지에 따라 `string2` 으로 수행합니다.  문자 사이는 차이점이 현재 코드 페이지에 순서와 lexicographic 문자 순서 설정 및 문자열 비교에 대한 관심의 차이가 있는 경우에 이러한 함수를 사용해야 합니다.  
  
 이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  하나 `string1` 또는 `string2` 는 널 포인터 경우, 또는 `count` 는보다 큰 `INT_MAX`, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명된데로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 비교할 두 문자열의 로캘 종속 작업이므로 각 로케일의 문자 순서에 대한 규칙입니다.  이 `_l` 접미사없이 이러한 기능의 버전이 로캘에 의존하는 행동에 대한 현재 스레드의 로캘을 사용합니다; `_l` 접미사 버전은 현재 로케일 대신의 매개 변수로 전달된 로캘을 사용하는 것을 제외하고는 접하지 않고 해당 기능과 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strcoll`|\<string.h\>|  
|`wcscoll`|\<wchar.h\>, \<string.h\>|  
|`_mbscoll`, `_mbscoll_l`|\<mbstring.h\>|  
|`_strcoll_l`|\<string.h\>|  
|`_wcscoll_l`|\<wchar.h\>, \<string.h\>|  
  
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