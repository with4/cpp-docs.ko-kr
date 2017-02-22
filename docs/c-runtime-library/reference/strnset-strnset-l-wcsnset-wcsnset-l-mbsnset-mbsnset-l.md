---
title: "_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnset"
  - "_strnset"
  - "_mbsnset_l"
  - "_wcsnset_l"
  - "_wcsnset"
  - "_strnset_l"
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
  - "_tcsncset_l"
  - "mbsnset_l"
  - "_tcsnset_l"
  - "_fstrnset"
  - "_wcsnset_l"
  - "_ftcsnset"
  - "wcsnset_l"
  - "_mbsnset_l"
  - "_strnset"
  - "_tcsnset"
  - "_strnset_l"
  - "mbsnset"
  - "strnset_l"
  - "_mbsnset"
  - "_wcsnset"
  - "_tcsncset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrnset 함수"
  - "_ftcsnset 함수"
  - "_mbsnset 함수"
  - "_mbsnset_l 함수"
  - "_strnset 함수"
  - "_strnset_l 함수"
  - "_tcsncset 함수"
  - "_tcsncset_l 함수"
  - "_tcsnset 함수"
  - "_tcsnset_l 함수"
  - "_wcsnset 함수"
  - "_wcsnset_l 함수"
  - "문자[C++], 서식으로 초기화"
  - "fstrnset 함수"
  - "ftcsnset 함수"
  - "문자 초기화"
  - "mbsnset 함수"
  - "mbsnset_l 함수"
  - "문자열[C++], 초기화"
  - "strnset_l 함수"
  - "tcsncset 함수"
  - "tcsnset 함수"
  - "tcsnset_l 함수"
  - "wcsnset_l 함수"
ms.assetid: 3f306489-5763-48e5-b939-aefee7c94ef5
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# _strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특정된 문자열의 문자를 주어진 문자로 초기화합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strnset\_s, \_strnset\_s\_l, \_wcsnset\_s, \_wcsnset\_s\_l, \_mbsnset\_s, \_mbsnset\_s\_l](../../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  `_mbsnset` 와 `_mbsnset_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strnset(  
   char *str,  
   int c,  
   size_t count   
);  
char *_strnset_l(  
   char *str,  
   int c,  
   size_t count,  
   locale_t locale  
);  
wchar_t *_wcsnset(  
   wchar_t *str,  
   wchar_t c,  
   size_t count   
);  
wchar_t *_wcsnset_l(  
   wchar_t *str,  
   wchar_t c,  
   size_t count,  
   _locale_t locale  
);  
unsigned char *_mbsnset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 변경할 문자열입니다.  
  
 `c`  
 문자 설정입니다.  
  
 `count`  
 바꿀 문자의 개수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 변경된 문자열에 대한 포인터를 반환합니다.  
  
## 설명  
 `_strnset` 함수는 첫 번째 `count` `str` 의 문자를 `c` 에 설정합니다. \(변환 `char`\).   `count`  이  `str` 의 길이보다 큰 경우,  `count` 대신에   `str`  이 사용됩니다.  
  
 `_wcsnset` 및 `_mbsnset` 는 와이드 문자 및 `_strnset`의 멀티 바이트 문자 버전입니다.  `_wcsnset` 의 인수 및 반환 값은 와이드 문자열이며, `_mbsnset` 는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `_mbsnset` 또는 `str` 이 null 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `_mbsnset` 는 널을 반환하고 `errno` 에서 `EINVAL`로 설정합니다.  `_strnset` 와 `_wcsnset` 는 매개 변수를 확인하지 않습니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며,`_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strnset`|\<string.h\>|  
|`_strnset_l`|\<tchar.h\>|  
|`_wcsnset`|\<string.h\> 또는 \<wchar.h\>|  
|`_wcsnset_l`|\<tchar.h\>|  
|`_mbsnset`, `_mbsnset_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strnset.c  
// compile with: /W3  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 characters of string to be *'s */  
   printf( "Before: %s\n", string );  
   _strnset( string, '*', 4 ); // C4996  
   // Note: _strnset is deprecated; consider using _strnset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
  **전:이것은 테스트입니다.**  
**후: \* \* \*이 테스트입니다.**   
## 해당 .NET Framework 항목  
 [System::String::Replace](https://msdn.microsoft.com/en-us/library/system.string.replace.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)