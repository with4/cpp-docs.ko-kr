---
title: "strcspn, wcscspn, _mbscspn, _mbscspn_l | Microsoft Docs"
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
  - "_mbscspn_l"
  - "wcscspn"
  - "_mbscspn"
  - "strcspn"
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
  - "strcspn"
  - "_mbscspn"
  - "wcscspn"
  - "_ftcscspn"
  - "_tcscspn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcscspn 함수"
  - "_mbscspn 함수"
  - "_mbscspn_l 함수"
  - "_tcscspn 함수"
  - "ftcscspn 함수"
  - "mbscspn 함수"
  - "mbscspn_l 함수"
  - "strcspn 함수"
  - "문자열[C++], 검색"
  - "tcscspn 함수"
  - "wcscspn 함수"
ms.assetid: f73f51dd-b533-4e46-ba29-d05c553708a6
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcspn, wcscspn, _mbscspn, _mbscspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자 집합에 속하는 문자가 문자열에서 처음 검색된 요소의 인덱스를 반환 합니다.  
  
> [!IMPORTANT]
>  `_mbschr` 와 `_mbschr_l`는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
size_t strcspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcscspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbscspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbscspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 검색할 Null 종료 문자열입니다.  
  
 `strCharSet`  
 Null 종료 문자 집합입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 함수에서 `strCharSet`에 있는 `str` 의 첫 번째 문자의 인덱스를 반환 합니다.  이 `str` 의 문자가 아닌 것이 `strCharSet` 에 있는 경우, 반환 값은 `str`의 길이입니다.  
  
 반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.  
  
## 설명  
 `wcscspn` 및 `_mbscspn` 는 와이드 문자 및 `strcspn`의 멀티 바이트 문자 버전입니다.  이 `wcscspn` 의 인수는 와이드 문자열이며, `_mbscspn` 는 멀티바이트 문자열입니다.  
  
 `_mbscspn` 매개 변수의 유효성을 검사합니다.  이 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `str` 또는 `strCharSet` 어느 쪽이 null 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 0을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  `strcspn` 와 `wcscspn` 는 매개 변수를 확인 하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscspn`|`strcspn`|`_mbscspn`|`wcscspn`|  
|`n/a`|`n/a`|`_mbscspn_l`|`n/a`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strcspn`|\<string.h\>|  
|`wcscspn`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbscspn`, `_mbscspn_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strcspn.c  
  
#include <string.h>  
#include <stdio.h>  
  
void test( const char * str, const char * strCharSet )  
{  
   int pos = strcspn( str, strCharSet );  
   printf( "strcspn( \"%s\", \"%s\" ) = %d\n", str, strCharSet, pos );      
}  
  
int main( void )  
{  
   test( "xyzbxz", "abc" );  
   test( "xyzbxz", "xyz" );  
   test( "xyzbxz", "no match" );  
   test( "xyzbxz", "" );  
   test( "", "abc" );  
   test( "", "" );  
}  
```  
  
  **strcspn\( "xyzbxz", "abc" \) \= 3**  
**strcspn\( "xyzbxz", "xyz" \) \= 0**  
**strcspn\( "xyzbxz", "no match" \) \= 6**  
**strcspn\( "xyzbxz", "" \) \= 6**  
**strcspn\( "", "abc" \) \= 0**  
**strcspn\( "", "" \) \= 0**   
## 해당 .NET Framework 항목  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)