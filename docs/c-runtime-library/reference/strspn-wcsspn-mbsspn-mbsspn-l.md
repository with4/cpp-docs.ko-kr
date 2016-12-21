---
title: "strspn, wcsspn, _mbsspn, _mbsspn_l | Microsoft Docs"
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
  - "_mbsspn_l"
  - "wcsspn"
  - "strspn"
  - "_mbsspn"
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
  - "_ftcsspn"
  - "wcsspn"
  - "_mbsspn"
  - "_tcsspn"
  - "strspn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsspn 함수"
  - "_mbsspn 함수"
  - "_mbsspn_l 함수"
  - "_tcsspn 함수"
  - "ftcsspn 함수"
  - "mbsspn 함수"
  - "mbsspn_l 함수"
  - "문자열[C++], 검색"
  - "strspn 함수"
  - "부분 문자열, 찾기"
  - "tcsspn 함수"
  - "wcsspn 함수"
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strspn, wcsspn, _mbsspn, _mbsspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자 집합에 속하지 않는 문자열의 첫 번째 문자의 인덱스를 반환합니다.  
  
> [!IMPORTANT]
>  `_mbsspn` 와 `_mbsspn_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
size_t strspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcsspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbsspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbsspn_l(  
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
 오로지 `strCharSet`*.* 로 구성된 `str` 인 문자열의 지정된 길이인 정수 값을 반환합니다. 이 `str` 이 `strCharSet`*,* 아닌 문자가 시작하는 경우, 함수는 0을 반환합니다.  
  
## 설명  
 이 `strspn` 함수는 `strCharSet` 의 문자 집합에 속하지 않는 `str` 인 첫 문자의 인덱스를 반환합니다.  검색은 종료되는 null 문자를 포함 하지 않습니다.  
  
 `wcsspn` 및 `_mbsspn` 는 와이드 문자 및 `strspn`**.** 의 멀티 바이트 문자 버전입니다. 이 `wcsspn` 의 인수는 와이드 문자열이며, `_mbsspn` 는 멀티바이트 문자열입니다.  `_mbsspn` 매개 변수의 유효성을 검사합니다.  이 `str` 혹은 `strCharSet` 가`NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `_mbspn` 는 `errno` 를 `EINVAL` 로 설정하고 0을 반환합니다.  `strspn` 와 `wcsspn` 는 매개 변수를 확인 하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsspn`|`strspn`|`_mbsspn`|`wcsspn`|  
|**해당 없음**|**해당 없음**|`_mbsspn_l`|**해당 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strspn`|\<string.h\>|  
|`wcsspn`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsspn`, `_mbsspn_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strspn.c  
// This program uses strspn to determine  
// the length of the segment in the string "cabbage"  
// consisting of a's, b's, and c's. In other words,  
// it finds the first non-abc letter.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "cabbage";  
   int  result;  
   result = strspn( string, "abc" );  
   printf( "The portion of '%s' containing only a, b, or c "  
           "is %d bytes long\n", string, result );  
}  
```  
  
  **'양배추' 부분 포함하는 a, b, c혹은 5 바이트 길이**   
## 해당 .NET Framework 항목  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strspnp, \_wcsspnp, \_mbsspnp, \_mbsspnp\_l](../../c-runtime-library/reference/strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)