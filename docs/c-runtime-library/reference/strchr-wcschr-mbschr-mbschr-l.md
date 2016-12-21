---
title: "strchr, wcschr, _mbschr, _mbschr_l | Microsoft Docs"
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
  - "strchr"
  - "wcschr"
  - "_mbschr_l"
  - "_mbschr"
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
  - "_ftcschr"
  - "strchr"
  - "wcschr"
  - "_tcschr"
  - "_mbschr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcschr 함수"
  - "_mbschr 함수"
  - "_mbschr_l 함수"
  - "_tcschr 함수"
  - "문자[C++], 문자열에서 찾기"
  - "ftcschr 함수"
  - "mbschr 함수"
  - "mbschr_l 함수"
  - "strchr 함수"
  - "문자열[C++], 검색"
  - "tcschr 함수"
  - "wcschr 함수"
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
caps.latest.revision: 31
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strchr, wcschr, _mbschr, _mbschr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘 또는 지정한 LC\_CTYPE 변환 상태 범주를 사용 하 여 문자열의 문자를 찾습니다.  
  
> [!IMPORTANT]
>  `_mbschr` 와 `_mbschr_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *strchr(  
   const char *str,  
   int c   
);  // C only  
char *strchr(  
   char * str,  
   int c   
); // C++ only  
const char *strchr(  
   const char * str,  
   int c   
); // C++ only  
wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcschr(  
   wchar_t *str,  
   wchar_t c   
);  // C++ only  
const wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
);  // C++ only  
unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbschr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only   
unsigned char *_mbschr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `str`  
 Null 종료 소스 문자열입니다.  
  
 `c`  
 쓰여질 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 첫 번째 항목에 대 한 포인터를 반환 각이 함수 `c` 에서 `str`, 또는 `NULL` 경우 `c` 찾을 수 없습니다.  
  
## 설명  
 `strchr` 함수의 첫 번째 항목을 찾습니다. `c` 에서 `str`, 반환 또는 `NULL` 경우 `c` 찾을 수 없습니다.  Null 종료 문자는 검색에 포함 됩니다.  
  
 `wcschr` , `_mbschr` 및 `_mbschr_l` 은 와이드 문자이고 `strchr`.의 멀티 바이트 문자 버전입니다.  `wcschr`의 인수 및 반환 값은 와이드 문자열이며, `_mbschr`는 멀티바이트 문자열입니다.  `_mbschr` 멀티 바이트 문자 시퀀스를 인식합니다.  이 `_mbschr` 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, `_mbschr` 은 `NULL` 를 반환하고, `errno` 에 `EINVAL`를 설정합니다.  `strchr` 와 `wcschr` 는 매개 변수를 확인하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C에서 이러한 함수는 첫 번째 인수에 대한 `const` 포인터를 갖습니다.  C\+\+에서는 두 오버로드를 모두 사용할 수 있습니다.  `const`에 대한 포인터를 갖는 오버로드는 `const`에 대한 포인터를 반환합니다. 비`const`에 대한 포인터를 갖는 버전은 비`const`에 대한 포인터를 반환합니다.  이러한 함수의 `const` 및 비`const` 버전을 모두 사용할 수 있는 경우 매크로 \_CONST\_CORRECT\_OVERLOADS가 정의됩니다.  두 C\+\+ 오버로드에 대한 비`const` 동작이 필요한 경우 기호 \_CONST\_RETURN을 정의합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcschr`|`strchr`|`_mbschr`|`wcschr`|  
|**N\/A**|**해당 없음**|`_mbschr_l`|**해당 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strchr`|\<string.h\>|  
|`wcschr`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbschr`, `_mbschr_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strchr.c  
//   
// This program illustrates searching for a character  
// with strchr (search forward) or strrchr (search backward).  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int  ch = 'r';  
  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
  
   printf_s( "String to be searched:\n      %s\n", string );  
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );  
   printf_s( "Search char:   %c\n", ch );  
  
   // Search forward.   
   pdest = strchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   first %c found at position %d\n",   
              ch, result );  
   else  
      printf_s( "Result:   %c not found\n", ch );  
  
   // Search backward.   
   pdest = strrchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   last %c found at position %d\n", ch, result );  
   else  
      printf_s( "Result:\t%c not found\n", ch );  
}  
```  
  
  **변경할 문자열입니다.**  
 **빠르고 교활한 여우가 게으른 갈색 개를 뛰어 넘었습니다.**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**문자 검색: r**  
**결과: 첫 번째 r 12 위치에서 발견**  
**결과: 마지막 r 30 위치에서 발견**   
## 해당 .NET Framework 항목  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strstr, wcsstr, \_mbsstr, \_mbsstr\_l](../../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)