---
title: "_strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsset_s"
  - "_wcsset_s_l"
  - "_strset_s"
  - "_mbsset_s_l"
  - "_strset_s_l"
  - "_mbsset_s"
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
  - "_wcsset_s_l"
  - "strset_s"
  - "_mbsset_s"
  - "mbsset_s"
  - "_strset_s"
  - "_mbsset_s_l"
  - "strset_s_l"
  - "_wcsset_s"
  - "mbsset_s_l"
  - "wcsset_s_l"
  - "wcsset_s"
  - "_strset_s_l"
  - "_tcsset_s_l"
  - "_tcsset_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsset_s 함수"
  - "_mbsset_s_l 함수"
  - "_strset_s 함수"
  - "_strset_s_l 함수"
  - "_tcsset_s 함수"
  - "_tcsset_s_l 함수"
  - "_wcsset_s 함수"
  - "_wcsset_s_l 함수"
  - "문자[C++], 설정"
  - "mbsset_s 함수"
  - "mbsset_s_l 함수"
  - "문자열[C++], 문자 설정"
  - "strset_s 함수"
  - "strset_s_l 함수"
  - "tcsset_s 함수"
  - "tcsset_s_l 함수"
  - "wcsset_s 함수"
  - "wcsset_s_l 함수"
ms.assetid: dceb2909-6b41-4792-acb7-888e45bb8b35
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자에 문자열의 문자를 설정합니다.  이러한 버전의 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  `_mbsset_s` 와 `_mbsset_s_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t _strset_s(  
   char *str,  
   size_t numberOfElements,  
   int c   
);  
errno_t _strset_s_l(  
   char *str,  
   size_t numberOfElements,  
   int c,  
   locale_t locale  
);  
errno_t _wcsset_s(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c   
);  
errno_t *_wcsset_s_l(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c,  
   locale_t locale  
);  
errno_t _mbsset_s(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c   
);  
errno_t _mbsset_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 설정할 Null 종료 문자열입니다.  
  
 `numberOfElements`  
 이 `str` 버퍼의 크기입니다.  
  
 `c`  
 문자 설정입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 오류 코드입니다.  
  
 이러한 함수는 해당 함수 인수의 유효성을 검사합니다.  이 `str` 가 null 포인터 혹은 `numberOfElements` 인수가 0과 같거나 작은 경우, 전달된 블록이 null로 끝나지 않는 경우, 그러면 잘못된 매개 변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명된 대로 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EINVAL` 을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
## 설명  
 이 `_strset_s` 함수는, 종료 null 문자를 제외하고, `str` 에서 \( `char`로 변환될\) `c` 인 모든 문자로 설정합니다.  `_wcsset_s` 및 `_mbsset_s` 는 와이드 문자 및 `_strset_s`의 멀티 바이트 문자 버전입니다.  인수 및 반환 값의 데이터 형식에 따라 달라집니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsset_s`|`_strset_s`|`_mbsset_s`|`_wcsset_s`|  
|`_tcsset_s_l`|`_strset_s_l`|`_mbsset_s_l`|`_wcsset_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strset_s`|\<string.h\>|  
|`_strset_s_l`|\<tchar.h\>|  
|`_wcsset_s`|\<string.h\> 또는 \<wchar.h\>|  
|`_wcsset_s_l`|\<tchar.h\>|  
|`_mbsset_s`, `_mbsset_s_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strset_s.c  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char string[] = "Fill the string with something.";  
   printf( "Before: %s\n", string );  
   _strset_s( string, _countof(string), '*' );  
   printf( "After:  %s\n", string );  
}  
```  
  
  **이전: 동물과 문자열을 채웁니다.**  
**후에: \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)