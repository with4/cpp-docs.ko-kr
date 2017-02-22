---
title: "strcmp, wcscmp, _mbscmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscmp"
  - "_mbscmp"
  - "strcmp"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbscmp"
  - "wcscmp"
  - "strcmp"
  - "_tcscmp"
  - "_ftcscmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscmp 함수"
  - "_mbscmp 함수"
  - "_tcscmp 함수"
  - "ftcscmp 함수"
  - "mbscmp 함수"
  - "strcmp 함수"
  - "문자열 비교[C++]"
  - "문자열[C++], 비교"
  - "tcscmp 함수"
  - "wcscmp 함수"
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# strcmp, wcscmp, _mbscmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비교 문자열입니다.  
  
> [!IMPORTANT]
>  `_mbscmp`는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### 매개 변수  
 `string1`, `string2`  
 비교할 Null 종료 문자열입니다.  
  
## 반환 값  
 이러한 각 함수의 반환 값은 `string1`에 대한 `string2`의 서수 관계를 나타냅니다.  
  
|값|문자열 1과 문자열 2의 관계|  
|-------|----------------------|  
|\< 0|`string1`이 `string2`보다 작은 경우|  
|0|`string1`이 `string2`와 같은 경우|  
|\> 0|`string1`이 `string2`보다 큰 경우|  
  
 매개 변수 유효성 검사 오류 시 `_mbscmp`는 \<string.h\> 및 \<mbstring.h\>에 정의된 `_NLSCMPERROR`를 반환합니다.  
  
## 설명  
 `strcmp` 함수는 `string1` 및 `string2`의 서수 비교를 수행하고 해당 관계를 나타내는 값을 반환합니다.  `wcscmp` 및 `_mbscmp`는 각각 `strcmp`의 와이드 문자 및 멀티바이트 문자 버전입니다.  `_mbscmp`는 현재 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 오류 발생 시 `_NLSCMPERROR`를 반환합니다.  자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md)를 참조하세요.  또한 `string1` 또는 `string2`가 null 포인터인 경우 `_mbscmp`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용한 경우 `_mbscmp`는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  `strcmp` 및 `wcscmp`는 매개 변수의 유효성을 검사하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 `strcmp` 함수가 `strcoll` 함수와 다른 점은 `strcmp` 비교는 서수이며 로캘의 영향을 받지 않는다는 것입니다.  `strcoll`은 현재 로캘의 `LC_COLLATE` 범주를 사용하여 문자열을 사전 순으로 비교합니다.  `LC_COLLATE` 범주에 대한 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  
  
 "C" 로캘에서 문자 집합\(ASCII 문자 집합\)의 순서는 사전적 문자 순서와 같습니다.  그러나 다른 로캘에서 문자 집합의 순서는 사전적 순서와 다를 수 있습니다.  예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'\(값 0x61\)는 문자 'ä'\(값 0xE4\) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.  
  
 문자 집합과 사전의 문자 순서가 서로 다른 로캘에서는 문자열의 사전 순 비교에 `strcoll` 대신 `strcmp`을 사용할 수 있습니다.  원본 문자열에서는 `strxfrm`을 사용하고 결과 문자열에서는 `strcmp`를 사용할 수도 있습니다.  
  
 `strcmp` 함수는 대소문자를 구분합니다.  `_stricmp`, `_wcsicmp` 및 `_mbsicmp`는 먼저 문자열을 소문자 형식으로 변환한 후에 문자열을 비교합니다.  ASCII 테이블의 'Z'와 'a' 사이에 있는 문자\('\[', '`\`', '\]', '`^`', '`_`', '```'\)를 포함하는 두 문자열은 대소문자에 따라 서로 다른 방식으로 비교됩니다.  예를 들어 두 문자열 `"ABCDE"` 및 `"ABCD^"`은 소문자\(`"abcde"` \> `"abcd^"`\)인 경우와 대문자\(`"ABCDE"` \< `"ABCD^"`\)인 경우에 다른 방법으로 비교됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strcmp`|\<string.h\>|  
|`wcscmp`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbscmp`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_strcmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Compare strings:**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown dog jumps over the lazy fox**  
 **strcmp:   String 1 is greater than string 2**  
 **\_stricmp:  String 1 is equal to string 2**   
## 해당 .NET Framework 항목  
 [System::String::CompareOrdinal](https://msdn.microsoft.com/en-us/library/system.string.compareordinal.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [\_memicmp, \_memicmp\_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)