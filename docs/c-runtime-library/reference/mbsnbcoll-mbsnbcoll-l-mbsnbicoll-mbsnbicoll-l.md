---
title: "_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l | Microsoft Docs"
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
  - "_mbsnbicoll_l"
  - "_mbsnbcoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbicoll"
  - "mbsnbcoll"
  - "mbsnbicoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
  - "_ftcsnicoll"
  - "_ftcsncoll"
  - "mbsnbcoll_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcoll 함수"
  - "_mbsnbcoll_l 함수"
  - "_mbsnbicoll 함수"
  - "_mbsnbicoll_l 함수"
  - "_tcsncoll 함수"
  - "_tcsnicoll 함수"
  - "mbsnbcoll 함수"
  - "mbsnbcoll_l 함수"
  - "mbsnbicoll 함수"
  - "mbsnbicoll_l 함수"
  - "tcsncoll 함수"
  - "tcsnicoll 함수"
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 코드 페이지 정보를 사용하여 멀티 바이트 2 문자 문자열을의 `n` 바이트를 비교하세요.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `string1, string2`  
 비교할 문자열입니다.  
  
 `count`  
 비교할 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 반환 값은 `string1` 과 `string2`의 부분 문자열의 관계를 나타냅니다.  
  
|반환 값|설명|  
|----------|--------|  
|\< 0|`string1` 부분 문자열 보다 작은 `string2` 부분 문자열.|  
|0|`string1` 부분 문자열이 동일한 `string2` 부분 문자열.|  
|\> 0|`string1` 부분 문자열 보다 큰 `string2` 부분 문자열.|  
  
 만약 `string1` 혹은 `string2` 이 `NULL` 혹은 `count` 이 `INT_MAX`보다 크다면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명된데로, 유효한 매개변수 처리기는 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  이 `_NLSCMPERROR`를 사용하여, String.h 혹은 Mbstring.h 어느 쪽을 포함합니다.  
  
## 설명  
 각 이러한 함수는, 최대한, `string1` 와 `string2` 의 첫 `count` 바이트에 비교하고 `string1` 과 `string2` 의 문자열 결과 사이를 관계성으로 나타내는 값을 반환합니다.  경우에 있는 부분 문자열의 마지막 바이트 `string1` 또는 `string2` 선행 바이트 인지; 비교에 포함되지 않고 이러한 함수만 완료 문자 부분 문자열에서을 비교합니다.  `_mbsnbicoll` 는 `_mbsnbcoll` 의 대\/소문자 버전입니다.  이 `_mbsnbcmp` 과 `_mbsnbicmp`같이, `_mbsnbcoll` 과 `_mbsnbicoll` 은 현재 사용하는 멀티 바이트 [코드 페이지](../../c-runtime-library/code-pages.md) 에 지정된 사진 편집의 순서에 따라 두 벌티 바이트 문자열을 비교합니다.  
  
 일부 코드 페이지와 해당 문자 집합에 대한 문자 집합에, 문자의 순서 lexicographic 문자 순서와에서 다를 수 있습니다.  "C" 로케일에서 이 경우가 아니라면: ASCII 문자 집합의 문자 순서는 문자 lexicographic 순서와 동일합니다.  그러나 특정 유럽 코드 페이지에서 예를 들어, 문자 'a' \(값 0x61\) 앞 문자 'ä' \(0xE4\)의 값은 문자 집합, 그러나 사전 순으로 문자를 제외한 문자 'ä' 앞에 'a' 입니다.  이 바이트에 의해 lexicographic 문자열 비교를 수행 하려면, 오히려 `_mbsnbcmp` 보다 `_mbsnbcoll` 을 사용합니다; 문자열이 같음을 확이하려면, `_mbsnbcmp` 을 사용합니다.  
  
 이 `coll` 함수는 사전순으로 비교한 문자열을 비교하기 때문에, `cmp` 함수는 같은 문자열을 쉽게 테스트하는 것 인데도 `coll` 함수는 같은 `cmp` 버전보다 더 많이 느립니다.  그럼에도, 문자 사이는 차이점이 현재 코드 페이지에 순서와 lexicographic 문자 순서 설정 및 비교에 대한 관심의 차이가 있는 경우에 `coll` 함수를 사용해야 합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncoll`|[\_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[\_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[\_wcsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[\_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[\_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[\_strnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[\_wcsnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbcoll`|\<mbstring.h\>|  
|`_mbsnbcoll_l`|\<mbstring.h\>|  
|`_mbsnbicoll`|\<mbstring.h\>|  
|`_mbsnbicoll_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)