---
title: "strncmp, wcsncmp, _mbsncmp, _mbsncmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
  - "_mbsncmp_l"
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
  - "_ftcsnccmp"
  - "_ftcsncmp"
  - "_tcsncmp"
  - "_tcsnccmp"
  - "strncmp"
  - "_mbsncmp"
  - "wcsncmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsnccmp 함수"
  - "_ftcsncmp 함수"
  - "_mbsncmp 함수"
  - "_mbsncmp_l 함수"
  - "_tcsnccmp 함수"
  - "_tcsncmp 함수"
  - "문자[C++], 비교"
  - "ftcsnccmp 함수"
  - "ftcsncmp 함수"
  - "mbsncmp 함수"
  - "mbsncmp_l 함수"
  - "문자열 비교[C++], strncmp 함수"
  - "문자열[C++], 문자 비교"
  - "strncmp 함수"
  - "tcsnccmp 함수"
  - "tcsncmp 함수"
  - "wcsncmp 함수"
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 문자열의 문자를 지정한 수까지 비교합니다.  
  
> [!IMPORTANT]
>  Windows 런타임에서 실행되는 응용 프로그램에서는 `_mbsncmp` 및 `_mbsncmp_l`을 사용할 수는 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
int strncmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int wcsncmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsncmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,   
   _locale_t locale  
);int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### 매개 변수  
 `string1, string2`  
 비교할 문자열입니다.  
  
 `count`  
 비교할 문자 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 반환 값은 다음과 같이 `string1` 및 `string2` 부분 문자열의 관계를 나타냅니다.  
  
|반환 값|설명|  
|----------|--------|  
|\< 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 작습니다.|  
|0|`string1` 부분 문자열이 `string2` 부분 문자열과 같습니다.|  
|\> 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 큽니다.|  
  
 매개 변수 유효성 검사 오류 시 `_mbsncmp` 및 `_mbsncmp_l`은 \<string.h\> 및 \<mbstring.h\>에 정의된 `_NLSCMPERROR`를 반환합니다.  
  
## 설명  
 `strncmp` 함수는 `count` 및 `string1`에서 최대 처음 `string2`개 문자까지 서수 비교를 수행한 다음 부분 문자열 간의 관계를 나타내는 값을 반환합니다.  `strncmp`는 대소문자를 구분하는 `_strnicmp` 버전입니다.  `wcsncmp` 및 `_mbsncmp`는 각각 대소문자를 구분하는 `_wcsnicmp` 및 `_mbsnicmp` 버전입니다.  
  
 `wcsncmp` 및 `_mbsncmp`는 `strncmp`의 와이드 문자 및 멀티바이트 문자 버전입니다.  `wcsncmp`의 인수는 와이드 문자열이고 `_mbsncmp`의 인수는 멀티바이트 문자열입니다.  `_mbsncmp`는 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 오류 발생 시 `_NLSCMPERROR`를 반환합니다.  
  
 또한 `_mbsncmp` 및 `_mbsncmp_l`은 매개 변수의 유효성을 검사합니다.  `string1` 또는 `string2`가 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용한 경우 `_mbsncmp` 및 `_mbsncmp_l`은 `_NLSCMPERROR`를 반환하며 `errno`는 `EINVAL`로 설정됩니다.  `strncmp` 및 `wcsncmp`는 매개 변수의 유효성을 검사하지 않습니다.  그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
 로캘의 `_mbsncmp` 범주 설정이 `_mbsncmp_l` 및 `LC_CTYPE`의 비교 동작에 영향을 줍니다.  이 설정은 멀티바이트 문자의 선행 및 후행 바이트 검색을 제어합니다.  자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  `_mbsncmp` 함수는 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다.  `_mbsncmp_l` 함수는 `locale` 매개 변수를 대신 사용한다는 점을 제외하면 이 함수와 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  싱글바이트 로캘의 경우 이러한 함수의 동작은 `strncmp`와 같습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnccmp`|`strncmp`|`_mbsncmp`|`wcsncmp`|  
|`_tcsncmp`|`strncmp`|`_mbsnbcmp`|`wcsncmp`|  
|`_tccmp`|매크로 또는 인라인 함수에 매핑|`_mbsncmp`|매크로 또는 인라인 함수에 매핑|  
|**적용할 수 없음**|**적용할 수 없음**|`_mbsncmp_l`|**적용할 수 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strncmp`|\<string.h\>|  
|`wcsncmp`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsncmp`, `_mbsncmp_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_strncmp.c  
#include <string.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n      %s\n      %s\n\n",  
           string1, string2 );  
   printf( "Function:   strncmp (first 10 characters only)\n" );  
   result = strncmp( string1, string2 , 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n\n", tmp );  
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );  
   result = _strnicmp( string1, string2, 10 );  
   if( result > 0 )  
      strcpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      strcpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:      String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Compare strings:**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown fox jumps over the lazy dog**  
**Function:   strncmp \(first 10 characters only\)**  
**Result:      String 1 is greater than string 2**  
**Function:   strnicmp \_strnicmp \(first 10 characters only\)**  
**Result:      String 1 is equal to string 2**   
## 해당 .NET Framework 항목  
 [System::String::Compare](frlrfSystemStringClassCompareTopic)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)