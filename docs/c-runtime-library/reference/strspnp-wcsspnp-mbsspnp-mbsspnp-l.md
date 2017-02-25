---
title: "_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsspnp"
  - "_wcsspnp"
  - "_mbsspnp_l"
  - "_strspnp"
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
  - "_tcsspnp"
  - "_mbsspnp"
  - "strspnp"
  - "_ftcsspnp"
  - "_mbsspnp_l"
  - "wcsspnp"
  - "mbsspnp_l"
  - "_wcsspnp"
  - "_strspnp"
  - "mbsspnp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsspnp 함수"
  - "_mbsspnp_l 함수"
  - "_strspnp 함수"
  - "_tcsspnp 함수"
  - "_wcsspnp 함수"
  - "mbsspnp 함수"
  - "mbsspnp_l 함수"
  - "strspnp 함수"
  - "tcsspnp 함수"
  - "wcsspnp 함수"
ms.assetid: 1ce18100-2edd-4c3b-af8b-53f204d80233
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 문자열에는 없는 제공된 문자열에서 첫 번째 문자로 포인터를 반환합니다.  
  
> [!IMPORTANT]
>  `_mbsspnp` 와 `_mbsspnp_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strspnp(  
   const char *str,  
   const char *charset  
);  
wchar_t *_wcsspnp(  
   const unsigned wchar_t *str,  
   const unsigned wchar_t *charset  
);  
unsigned char *_mbsspnp(  
   const unsigned char *str,  
   const unsigned char *charset  
);  
unsigned char *_mbsspnp_l(  
   const unsigned char *str,  
   const unsigned char *charset,  
   _locale_t locale  
);  
  
```  
  
#### 매개 변수  
 `str`  
 검색할 Null 종료 문자열입니다.  
  
 `charset`  
 Null 종료 문자 집합입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_strspnp`, `_wcsspnp`, 및 `_mbsspnp` 의 첫 번째 문자에 대한 포인터를 반환합니다. 이는 `str` 은 문자 집합 `charset`*.*이 속하지 않습니다. 이러한 각 함수는 `NULL` 을 반환합니다. `str` 은 `charset`*.*에서 문자 구성을 포함할 경우입니다. 이러한 각각의 루틴에 대한 반환 값은 오류를 나타내기 위해 예약 되어 있지 않습니다.  
  
## 설명  
 `_mbsspnp` 함수에서 첫 번째 문자는 멀티 바이트 문자에 대 한 포인터를 반환합니다. `str` 은 `charset` 문자집합에 속하지 않습니다.  `_mbsspnp` 멀티 바이트 문자 시퀀스에 따라 인식된 [멀티 바이트 코드 페이지](../../c-runtime-library/code-pages.md) 에서 현재 사용 중입니다.  검색은 종료되는 null 문자를 포함 하지 않습니다.  
  
 `str` 또는 `charset` 은 null 포인터입니다. 이 함수는 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로서 잘못된 매개변수 핸들러를 적용합니다.  계속해서 실행하도록 허용된 경우, 함수는 `NULL` 를 반환하고 `errno` 을 `EINVAL`으로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsspnp`|`_strspnp`|`_mbsspnp`|`_wcsspnp`|  
  
 `_strspnp` 와 `_wcsspnp` 는 와이드 문자 및 `_mbsspnp`의 멀티 바이트 문자 버전입니다.  `_strspnp` 및 `_wcsspnp` 은 `_mbsspnp` 에서 동일하게 작동됩니다. 반면에 ;이 매핑에 대해서만 제공하며 다른 이유로 사용할 수 없습니다.  자세한 내용은 [제네릭 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [제네릭 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md) 을 참조하십시오.  
  
 `_mbsspnp_l` 는 전달된 로캘을 사용한다는 점을 제외하고 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsspnp`|\<mbstring.h\>|  
|`_strspnp`|\<tchar.h\>|  
|`_wcsspnp`|\<tchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_mbsspnp.c  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void ) {  
   const unsigned char string1[] = "cabbage";  
   const unsigned char string2[] = "c";  
   unsigned char *ptr = 0;  
   ptr = _mbsspnp( string1, string2 );  
   printf( "%s\n", ptr);  
}  
```  
  
## Output  
  
```  
abbage  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)