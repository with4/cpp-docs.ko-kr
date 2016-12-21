---
title: "strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l | Microsoft Docs"
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
  - "strncat"
  - "_strncat_l"
  - "_mbsncat"
  - "_mbsncat_l"
  - "wcsncat"
  - "wcsncat_l"
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
  - "_tcsncat_l"
  - "_wcsncat_l"
  - "_tcsnccat_l"
  - "_mbsncat"
  - "_strncat_l"
  - "strncat"
  - "_tcsnccat"
  - "_mbsncat_l"
  - "_ftcsncat"
  - "wcsncat"
  - "_tcsncat"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsncat 함수"
  - "_mbsncat 함수"
  - "_mbsncat_l 함수"
  - "_tcsncat 함수"
  - "_tcsncat_l 함수"
  - "_tcsnccat 함수"
  - "_tcsnccat_l 함수"
  - "문자열 추가"
  - "문자[C++], 문자열에 추가"
  - "문자열 연결"
  - "ftcsncat 함수"
  - "mbsncat 함수"
  - "mbsncat_l 함수"
  - "문자열 연결[C++]"
  - "문자열[C++], 추가"
  - "strncat 함수"
  - "tcsncat 함수"
  - "tcsncat_l 함수"
  - "tcsnccat 함수"
  - "tcsnccat_l 함수"
  - "wcsncat 함수"
ms.assetid: de67363b-68c6-4ca5-91e3-478610ad8159
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 문자를 추가합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) 를 참조하십시오.  
  
> [!IMPORTANT]
>  `_mbsncat` 와 `_mbsncat_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *strncat(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
wchar_t *wcsncat(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
unsigned char *_mbsncat(  
   unsigned char *strDest,  
   const unsigned char *strSource,  
   size_t count  
);  
unsigned char *_mbsncat_l(  
   unsigned char *strDest,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
char *strncat(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
wchar_t *wcsncat(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsncat(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
unsigned char *_mbsncat_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `strDest`  
 Null\-종료된 대상 문자열.  
  
 `strSource`  
 Null 종료 소스 문자열입니다.  
  
 `count`  
 추가할 문자 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 목적지 문자열에 대한 포인터를 반환합니다.  반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.  
  
## 설명  
 이 `strncat` 함수는 `strSource` 의 문자의 `count` 에서 `strDest` 로 최대한 덧붙입니다.  `strSource` 의 시작 문자는 `strDest`의 null 종결 문자를 덮어씁니다.  이 `count` 문자가 덧붙여지기전, null 문자가 `strSource` 에 발생하는 경우, `strncat` 은 null 문자를 추가한 `strSource`로 부터 모든 문자를 덧붙입니다.  이 `count` 이 `strSource`의 길이보다 큰 경우, `count` 장소에 `strSource` 이 사용됩니다.  모든 경우 결과 문자열은 null 문자로 종료 됩니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `strncat` 은 `strDest` 의 충분한 공간을 확인하지 않습니다; 따라서 버퍼 오버런의 잠재적인 원인이 됩니다.  이 `count` 는 추가한 문자의 숫자를 제한하는 것을 명심하세요; `strDest` 의 크기의 제한은 없습니다.  다음 예제를 참조하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
 `wcsncat` 및 `_mbsncat` 는 와이드 문자 및 `strncat`의 멀티 바이트 문자 버전입니다.  이 `wcsncat` 의 인수 및 반환 값은 와이드 문자열이며, `_mbsncat` 는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C\+\+에서는 이러한 함수 템플릿 오버 로드 되어 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncat`|`strncat`|`_mbsnbcat`|`wcsncat`|  
|`_tcsncat_l`|`_strncat_l`|`_mbsnbcat_l`|`_wcsncat_l`|  
  
> [!NOTE]
>  `_strncat_l` 및 `_wcsncat_l` 는 로캘 종속성 없고 직접 호출할 수 없습니다.  이는 `_tcsncat_l` 을 사용하면서 내부에 제공됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strncat`|\<string.h\>|  
|`wcsncat`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsncat`|\<mbstring.h\>|  
|`_mbsncat_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strncat.c  
// Use strcat and strncat to append to a string.  
#include <stdlib.h>  
  
#define MAXSTRINGLEN 39  
  
char string[MAXSTRINGLEN+1];  
// or char *string = malloc(MAXSTRINGLEN+1);  
  
void BadAppend( char suffix[], int n )  
{  
   strncat( string, suffix, n );  
}  
  
void GoodAppend( char suffix[], size_t n )  
{  
   strncat( string, suffix, __min( n, MAXSTRINGLEN-strlen(string)) );  
}  
  
int main( void )  
{  
   string[0] = '\0';  
   printf( "string can hold up to %d characters\n", MAXSTRINGLEN );  
  
   strcpy( string, "This is the initial string!" );  
   // concatenate up to 20 characters...  
   BadAppend( "Extra text to add to the string...", 20 );  
   printf( "After BadAppend :  %s (%d chars)\n", string, strlen(string) );  
  
   strcpy( string, "This is the initial string!" );  
   // concatenate up to 20 characters...  
   GoodAppend( "Extra text to add to the string...", 20 );  
   printf( "After GoodAppend:  %s (%d chars)\n", string, strlen(string) );  
}  
```  
  
## Output  
  
```  
string can hold up to 39 characters  
After BadAppend :  This is the initial string!Extra text to add to (47 chars)  
After GoodAppend:  This is the initial string!Extra text t (39 chars)  
```  
  
 이 `BadAppend` 는 버퍼 오버런이 발생 합니다.  
  
## 해당 .NET Framework 항목  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)