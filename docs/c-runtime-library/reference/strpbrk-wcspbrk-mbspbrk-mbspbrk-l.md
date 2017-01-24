---
title: "strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs"
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
  - "_mbspbrk"
  - "wcspbrk"
  - "_mbspbrk_l"
  - "strpbrk"
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
  - "_fstrpbrk"
  - "_mbspbrk"
  - "strpbrk"
  - "_tcspbrk"
  - "_ftcspbrk"
  - "wcspbrk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstrpbrk 함수"
  - "_ftcspbrk 함수"
  - "_mbspbrk 함수"
  - "_mbspbrk_l 함수"
  - "_tcspbrk 함수"
  - "문자 집합[C++], 문자열에서 문자 스캔"
  - "문자[C++], 문자열 스캔"
  - "fstrpbrk 함수"
  - "ftcspbrk 함수"
  - "mbspbrk 함수"
  - "mbspbrk_l 함수"
  - "문자열[C++], 스캔"
  - "strpbrk 함수"
  - "tcspbrk 함수"
  - "wcspbrk 함수"
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 문자 집합에서 문자에 대한 문자열을 검색합니다.  
  
> [!IMPORTANT]
>  `_mbspbrk` 와 `_mbspbrk_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `str`  
 검색할 Null 종료 문자열입니다.  
  
 `strCharSet`  
 Null 종료 문자 집합입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 두 개의 문자열 인수는 공통 문자가 없는 경우, `str` 또는 `NULL` 포인터에서 `strCharSet` 로부터 모든 문자의 첫번째 발생 포인터를 반환합니다.  
  
## 설명  
 `strpbrk` 함수는 `strCharSet` 에서 문자 집합에 속하는 `str` 에서 문자의 첫번째 발생 하는 포인터를 반환합니다.  검색은 종료되는 null 문자를 포함 하지 않습니다.  
  
 `wcspbrk` 및 `_mbspbrk` 는 와이드 문자 및 `strpbrk`의 멀티 바이트 문자 버전입니다.  `wcspbrk`의 인수 및 반환 값은 와이드 문자열이며, `_mbspbrk`는 멀티바이트 문자열입니다.  
  
 `_mbspbrk` 매개 변수의 유효성을 검사합니다.  만일 `str` 혹은 `strCharSet` 가 `NULL` 이라면, 잘못된 매개 변수 처리기가 호출됩니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명되어 있습니다.  계속해서 실행하도록 허용된 경우, `_mbspbrk` 는 `NULL` 을 반환하고, `errno` 에 `EINVAL`를 설정합니다.  `strpbrk` 와 `wcspbrk` 는 매개 변수를 확인하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 `_mbspbrk` 는 `_mbscspn` 와 유사합니다. `_mbspbrk` 은 [size\_t](../../c-runtime-library/standard-types.md) 형식 값보다 포인터를 반환한다는 사실을 제외합니다.  
  
 C에서 이러한 함수는 첫 번째 인수에 대한 `const` 포인터를 갖습니다.  C\+\+에서는 두 오버로드를 모두 사용할 수 있습니다.  `const`에 대한 포인터를 갖는 오버로드는 `const`에 대한 포인터를 반환합니다. 비`const`에 대한 포인터를 갖는 버전은 비`const`에 대한 포인터를 반환합니다.  이러한 함수의 `const` 및 비`const` 버전을 모두 사용할 수 있는 경우 매크로 \_CONST\_CORRECT\_OVERLOADS가 정의됩니다.  두 C\+\+ 오버로드에 대한 비`const` 동작이 필요한 경우 기호 \_CONST\_RETURN을 정의합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**해당 없음**|**해당 없음**|`_mbspbrk_l`|**해당 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strpbrk`|\<string.h\>|  
|`wcspbrk`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
  **1: 3명의 남자와 2명의 소년은 5마리의 돼지를 먹었다.**  
**2: 3명의 남자와 2명의 소년은 5마리의 돼지를 먹었다.**  
**3: 2명의 소년은 5마리의 돼지를 먹었다.**  
**4: 5마리 돼지**   
## 해당 .NET Framework 항목  
 [System::String::IndexOfAny](https://msdn.microsoft.com/en-us/library/system.string.indexofany.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)