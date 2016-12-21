---
title: "strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l | Microsoft Docs"
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
  - "_mbslen"
  - "_mbslen_l"
  - "_mbstrlen"
  - "wcslen"
  - "_mbstrlen_l"
  - "strlen"
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
  - "_mbstrlen"
  - "wcslen"
  - "_tcslen"
  - "_ftcslen"
  - "strlen"
  - "_mbslen"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcslen 함수"
  - "_mbslen 함수"
  - "_mbslen_l 함수"
  - "_mbstrlen 함수"
  - "_mbstrlen_l 함수"
  - "_tcslen 함수"
  - "ftcslen 함수"
  - "길이, 문자열"
  - "mbslen 함수"
  - "mbslen_l 함수"
  - "mbstrlen 함수"
  - "mbstrlen_l 함수"
  - "문자열 길이, 가져오기"
  - "문자열[C++], 길이 가져오기"
  - "strlen 함수"
  - "tcslen 함수"
  - "wcslen 함수"
ms.assetid: 16462f2a-1e0f-4eb3-be55-bf1c83f374c2
caps.latest.revision: 32
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘 또는 지정된 로캘을 사용하여 문자열의 길이를 가져옵니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [strnlen, strnlen\_s, wcsnlen, wcsnlen\_s, \_mbsnlen, \_mbsnlen\_l, \_mbstrnlen, \_mbstrnlen\_l](../../c-runtime-library/reference/strnlen-strnlen-s.md)를 참조하세요.  
  
> [!IMPORTANT]
>  `_mbslen`, `_mbslen_l`, `_mbstrlen` 및 `_mbstrlen_l`는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
size_t strlen(    const char *str ); size_t wcslen(    const wchar_t *str  ); size_t _mbslen(    const unsigned char *str  ); size_t _mbslen_l(    const unsigned char *str,    _locale_t locale ); size_t _mbstrlen(    const char *str ); size_t _mbstrlen_l(    const char *str,    _locale_t locale );  
```  
  
#### 매개 변수  
 `str`  
 Null 종료 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 함수는 터미널 `NULL`을 제외하고 `str`의 문자 수를 반환합니다.  문자열에 잘못된 멀티바이트 문자가 포함된 경우`((size_t)(-1))`을 반환하는 `_mbstrlen` 및 `_mbstrlen_l`을 제외하고 오류를 나타내도록 예약된 반환 값은 없습니다.  
  
## 설명  
 `strlen`은 문자열을 싱글바이트 문자열로 해석하므로 문자열에 멀티바이트 문자가 포함되어 있더라도 해당 반환 값은 항상 바이트 수와 동일합니다.  `wcslen`은 `strlen`의 와이드 문자 버전이고 `wcslen`의 인수는 와이드 문자열이고 문자 수는 와이드\(2바이트\) 문자로 계산합니다.  그렇지 않으면 `wcslen`과 `strlen`이 동일하게 작동합니다.  
  
 **보안 정보** 다음 함수는 버퍼 오버런 문제로 인해 발생하는 잠재적인 위협을 일으킵니다.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcslen`|`strlen`|`strlen`|`wcslen`|  
|`_tcsclen`|`strlen`|`_mbslen`|`wcslen`|  
|`_tcsclen_l`|`strlen`|`_mbslen_l`|`wcslen`|  
  
 `_mbslen` 및 `_mbslen_l`은 멀티바이트 문자열의 멀티바이트 문자 수를 반환하지만 멀티바이트 문자의 유효성을 테스트하지는 않습니다.  `_mbstrlen` 및 `_mbstrlen_l`은 멀티바이트 문자의 유효성을 테스트하고 멀티바이트 문자 시퀀스를 인식합니다.  `_mbstrlen` 또는 `_mbstrlen_l`에 전달된 문자열에 코드 페이지에 대해 잘못된 멀티바이트 문자가 포함되어 있으면 이 함수는 \-1을 반환하고 `errno`를 `EILSEQ`로 설정합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strlen`|\<string.h\>|  
|`wcslen`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbslen`, `_mbslen_l`|\<mbstring.h\>|  
|`_mbstrlen`, `_mbstrlen_l`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_strlen.c  
// Determine the length of a string. For the multi-byte character  
// example to work correctly, the Japanese language support for  
// non-Unicode programs must be enabled by the operating system.  
  
#include <string.h>  
#include <locale.h>  
  
int main()  
{  
   char* str1 = "Count.";  
   wchar_t* wstr1 = L"Count.";  
   char * mbstr1;  
   char * locale_string;  
  
   // strlen gives the length of single-byte character string  
   printf("Length of '%s' : %d\n", str1, strlen(str1) );  
  
   // wstrlen gives the length of a wide character string  
   wprintf(L"Length of '%s' : %d\n", wstr1, wcslen(wstr1) );  
  
   // A multibyte string: [A] [B] [C] [katakana A] [D] [\0]  
   // in Code Page 932. For this example to work correctly,  
   // the Japanese language support must be enabled by the  
   // operating system.  
   mbstr1 = "ABC" "\x83\x40" "D";  
  
   locale_string = setlocale(LC_CTYPE, "Japanese_Japan");  
  
   if (locale_string == NULL)  
   {  
      printf("Japanese locale not enabled. Exiting.\n");  
      exit(1);  
   }  
   else  
   {  
      printf("Locale set to %s\n", locale_string);  
   }  
  
   // _mbslen will recognize the Japanese multibyte character if the  
   // current locale used by the operating system is Japanese  
   printf("Length of '%s' : %d\n", mbstr1, _mbslen(mbstr1) );  
  
   // _mbstrlen will recognize the Japanese multibyte character  
   // since the CRT locale is set to Japanese even if the OS locale  
   // isnot.   
   printf("Length of '%s' : %d\n", mbstr1, _mbstrlen(mbstr1) );  
   printf("Bytes in '%s' : %d\n", mbstr1, strlen(mbstr1) );     
  
}  
```  
  
  **'Count.'의 길이 : 6**  
**'Count.'의 길이 : 6**  
**'ABCァD'의 길이: 5**  
**'ABCァD'의 길이: 5**  
**'ABCァD'의 바이트 수: 6**   
## 해당 .NET Framework 항목  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)