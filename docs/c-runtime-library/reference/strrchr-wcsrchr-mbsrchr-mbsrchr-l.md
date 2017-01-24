---
title: "strrchr, wcsrchr, _mbsrchr, _mbsrchr_l | Microsoft Docs"
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
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
  - "_mbsrchr_l"
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
  - "_tcsrchr"
  - "_ftcsrchr"
  - "strrchr"
  - "wcsrchr"
  - "_mbsrchr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsrchr 함수"
  - "_mbsrchr 함수"
  - "_mbsrchr_l 함수"
  - "_tcsrchr 함수"
  - "문자[C++], 스캔"
  - "ftcsrchr 함수"
  - "mbsrchr 함수"
  - "mbsrchr_l 함수"
  - "문자열 스캔"
  - "문자열[C++], 스캔"
  - "strrchr 함수"
  - "tcsrchr 함수"
  - "wcsrchr 함수"
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strrchr, wcsrchr, _mbsrchr, _mbsrchr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마지막으로 문자에대한 문자열을 검색합니다.  
  
> [!IMPORTANT]
>  `_mbsrchr` 와 `_mbsrchr_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *strrchr(  
   const char *str,  
   int c   
); // C only  
char *strrchr(  
   char *str,  
   int c   
); // C++ only  
const char *strrchr(  
   const char *str,  
   int c   
); // C++ only  
wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcsrchr(  
   wchar_t *str,  
   wchar_t c   
); // C++ only  
const wchar_t *wcsrchr(  
   const wchar_t *str,  
   wchar_t c   
); // C++ only  
unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbsrchr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbsrchr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only  
unsigned char *_mbsrchr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsrchr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `str`  
 검색할 Null 종료 문자열입니다.  
  
 `c`  
 쓰여질 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 마지막으로 나오는 `c` 인 포인터를 `str` 또는 `NULL` 에서 반환합니다. `c` 를 찾을 수 없을 경우입니다.  
  
## 설명  
 이 `strrchr` 함수는 마지막 발생지역인 `c` 를 \( `char`를 변환\) `str`에서 찾습니다.  검색 종료에 null 문자를 포함합니다.  
  
 `wcsrchr` 및 `_mbsrchr` 는 와이드 문자 및 `strrchr`의 멀티 바이트 문자 버전입니다.  `wcsrchr` 의 인수 및 반환 값은 와이드 문자열이며, `_mbsrchr` 는 멀티바이트 문자열입니다.  
  
 C에서 이러한 함수는 첫 번째 인수에 대한 `const` 포인터를 갖습니다.  C\+\+에서는 두 오버로드를 모두 사용할 수 있습니다.  `const`에 대한 포인터를 갖는 오버로드는 `const`에 대한 포인터를 반환합니다. 비`const`에 대한 포인터를 갖는 버전은 비`const`에 대한 포인터를 반환합니다.  이러한 함수의 `const` 및 비`const` 버전을 모두 사용할 수 있는 경우 매크로 \_CONST\_CORRECT\_OVERLOADS가 정의됩니다.  두 C\+\+ 오버로드에 대한 비`const` 동작이 필요한 경우 기호 \_CONST\_RETURN을 정의합니다.  
  
 `_mbsrchr` 매개 변수의 유효성을 검사합니다.  `str`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, `errno` 및 `EINVAL` 는 `_mbsrchr` 를 반환하고 를 로 설정합니다.  `strrchr` 와 `wcsrchr` 는 매개 변수를 확인하지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|  
|**해당 없음**|**해당 없음**|`_mbsrchr_l`|**해당 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strrchr`|\<string.h\>|  
|`wcsrchr`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 `strrchr`를 사용하는 예제를 보려면 [](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md "strchr, wcschr, _mbschr, _mbschr_l")를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::String::LastIndexOf](https://msdn.microsoft.com/en-us/library/system.string.lastindexof.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)