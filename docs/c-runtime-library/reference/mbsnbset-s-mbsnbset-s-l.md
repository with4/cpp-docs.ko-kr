---
title: "_mbsnbset_s, _mbsnbset_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
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
  - "mbsnbset_s"
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
  - "mbsnbset_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbset_s 함수"
  - "_mbsnbset_s_l 함수"
  - "_tcsnset_s 함수"
  - "_tcsnset_s_l 함수"
  - "mbsnbset_s 함수"
  - "mbsnbset_s_l 함수"
  - "tcsnset_s 함수"
  - "tcsnset_s_l 함수"
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _mbsnbset_s, _mbsnbset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티바이트 문자열의 처음 `n`바이트를 지정된 문자로 설정합니다.  이 버전의 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
errno_t _mbsnbset_s(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count   
);  
errno_t _mbsnbset_s_l(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbset_s(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbset_s_l(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `str`  
 변경할 문자열입니다.  
  
 `size`  
 문자열 버퍼의 크기입니다.  
  
 `c`  
 단일 바이트나 멀티바이트 문자 설정입니다.  
  
 `count`  
 설정할 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 오류 코드입니다.  
  
## 설명  
 `_mbsnbset_s` 및 `_mbsnbset_s_l` 함수는 최대한 `str`의 처음 `count`바이트를 `c`로 설정합니다.  `count`가 `str`의 길이보다 큰 경우 `str`의 길이가 `count` 대신 사용됩니다.  `c`가 멀티바이트 문자이고 `count`에 지정된 마지막 바이트에 전체가 들어맞지 않는 경우 마지막 바이트는 빈 문자로 채워집니다.  `_mbsnbset_s` 및 `_mbsnbset_s_l`은 `str` 끝에 null 종결 문자를 배치하지 않습니다.  
  
 `_mbsnbset_s` 및 `_mbsnbset_s_l`은 `c`의 `count` 문자가 아니라 `count`바이트를 설정한다는 점을 제외하고는 `_mbsnset`와 유사합니다.  
  
 `str`이 `NULL`이거나 `count`가 0인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 예외를 생성합니다.  계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `NULL`을 반환합니다.  또한 `c`가 유효한 멀티바이트 문자가 아닌 경우 `errno`는 `EINVAL`로 설정되고 대신 공백이 사용됩니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  `_mbsnbset_s` 버전의 이 함수 이 로캘 종속 동작의 현재 로캘을 사용하고 `_mbsnbset_s_l` 버전은 전달된 로캘 매개 변수를 사용한다는 점을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C\+\+에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnset_s`|`_strnset_s`|`_mbsnbset_s`|`_wcsnset_s`|  
|`_tcsnset_s_l`|`_strnset_s _l`|`_mbsnbset_s_l`|`_wcsnset_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbset_s`|\<mbstring.h\>|  
|`_mbsnbset_s_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_mbsnbset_s.c  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset_s( string, sizeof(string), '*', 4 );  
   printf( "After:  %s\n", string );  
}  
```  
  
## 출력  
  **전: 테스트**  
**후:  \*\*\*\* 테스트**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)