---
title: "strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l | Microsoft Docs"
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
  - "_wcsncat_s_l"
  - "wcsncat_s"
  - "_mbsncat_s_l"
  - "_mbsncat_s"
  - "strncat_s"
  - "_strncat_s_l"
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
  - "strncat_s_l"
  - "_mbsncat_s_l"
  - "_tcsncat_s"
  - "wcsncat_s"
  - "wcsncat_s_l"
  - "strncat_s"
  - "_mbsncat_s"
  - "_tcsncat_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsncat_s 함수"
  - "_mbsncat_s_l 함수"
  - "_tcsncat_s 함수"
  - "_tcsncat_s_l 함수"
  - "문자열 추가"
  - "문자열 연결"
  - "mbsncat_s 함수"
  - "mbsncat_s_l 함수"
  - "문자열 연결[C++]"
  - "문자열[C++], 추가"
  - "strncat_s 함수"
  - "strncat_s_l 함수"
  - "wcsncat_s 함수"
  - "wcsncat_s_l 함수"
ms.assetid: de77eca2-4d9c-4e66-abf2-a95fefc21e5a
caps.latest.revision: 42
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 문자를 추가합니다.  이러한 버전의 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  `_mbsncat_s` 와 `_mbsncat_s_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t strncat_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncat_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncat_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncat_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncat_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count  
);  
errno_t _mbsncat_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t strncat_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncat_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncat_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncat_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `strDest`  
 Null\-종료된 대상 문자열.  
  
 \[in\]`numberOfElements`  
 대상 버퍼의 크기입니다.  
  
 \[in\]`strSource`  
 Null 종료 소스 문자열입니다.  
  
 \[in\]`count`  
 추가 혹은 [\_TRUNCATE](../../c-runtime-library/truncate.md) 할 문자 수입니다.  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공 시 0을 반환하고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`strDestination`|`numberOfElements`|`strSource`|반환 값|`strDestination`의 내용입니다.|  
|----------------------|------------------------|-----------------|----------|------------------------------|  
|`NULL` 나 종료 되지 않은|any|any|`EINVAL`|수정 안 됨|  
|any|any|`NULL`|`EINVAL`|수정 안 됨|  
|any|0 또는 너무 작습니다.|any|`ERANGE`|수정 안 됨|  
  
## 설명  
 이러한 함수는, `D` 이 `count` 과 `strSource` 길이 보더 더 적은 곳에 있는 , `strDest` 의 끝에 있는 `strSource` 의 첫 `D` 문자를 추가를 시도합니다.  그 `D` 문자가 \( `numberOfElements`로 크기가 지정된\) `strDest` 내부에 꽉 맞거나 null 종료 공간에서 여전히 떠날 수 있는 경우, 그러면 그 문자는 추가되고, `strDest`의 원래 null 종료로 시작하고, 새로운 종료 nul은 추가됩니다; 그렇지 않으면, `strDest`\[0\]은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명한데로 null문자와 유효하지 않는 매개 변수 처리기를 추가되고 설정합니다.  
  
 위의 단락에 예외가 있습니다.  만약 `count` 이 [\_TRUNCATE](../../c-runtime-library/truncate.md) 인 경우 종료 null 이 추가되는 공간을 여전히 남겨둔 체 그러면 맞춤에 `strSource` 가 `strDest` 가 추가되는 것이 많습니다.  
  
 예를 들면 다음과 같습니다.  
  
 `char dst[5];`  
  
 `strncpy_s(dst, _countof(dst), "12", 2);`  
  
 `strncat_s(dst, _countof(dst), "34567", 3);`  
  
 다섯 문자의 길이 버퍼안의 두 문자에서 세 문자로 추가된 `strncat_s` 의미합니다; 이는 null 종결자의 공간 없이 떠날 수 없으므로, `strncat_s` 0은 문자열을 출력하고 잘못된 매개 변수 처리기를 호출합니다.  
  
 잘라내기 동작이 필요한 경우, `_TRUNCATE` 을 사용하거나 `size` 매개 변수가 덧붙여져 조정합니다 :  
  
 `strncat_s(dst, _countof(dst), "34567", _TRUNCATE);`  
  
 또는  
  
 `strncat_s(dst, _countof(dst), "34567", _countof(dst)-strlen(dst)-1);`  
  
 모든 경우에서, 결과 문자열은 null 문자로 종료 됩니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 이 `strSource` 혹은 `strDest` 이 `NULL` 이거나 `numberOfElements` 이 0인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  실행이 계속 허용되지 않는 경우, 함수는 매개 변수가 수정됨이 없이 `EINVAL` 을 반환합니다.  
  
 `wcsncat_s` 및 `_mbsncat_s` 는 와이드 문자 및 `strncat_s`의 멀티 바이트 문자 버전입니다.  이 `wcsncat_s` 의 인수 및 반환 값은 와이드 문자열이며, `_mbsncat_s` 는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncat_s`|`strncat_s`|`_mbsnbcat_s`|`wcsncat_s`|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
 `_strncat_s_l` 및 `_wcsncat_s_l` 은 로캘 의존성이 없습니다; 이들은 `_tcsncat_s_l` 만 제공됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strncat_s`|\<string.h\>|  
|`wcsncat_s`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsncat_s`, `_mbsncat_s_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strncat_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncat_s_tester( const char * initialDest,  
                          const char * src,  
                          int count )  
{  
   char dest[10];  
   strcpy_s( dest, _countof(dest), initialDest );  
  
   printf_s( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf_s( "Appending '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf_s( "Appending %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   printf_s( "    old contents of dest: '%s'\n", dest );  
  
   errno_t err = strncat_s( dest, _countof(dest), src, count );  
  
   printf_s( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncat_s_tester( "hi ", "there", 4 );  
   strncat_s_tester( "hi ", "there", 5 );  
   strncat_s_tester( "hi ", "there", 6 );  
  
   printf_s( "\nDestination buffer too small:\n" );  
   strncat_s_tester( "hello ", "there", 4 );  
  
   printf_s( "\nTruncation examples:\n" );  
  
   errno_t err = strncat_s_tester( "hello ", "there", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncat_s_tester( "hello ", "!", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf_s( "\nSecure template overload example:\n" );  
  
   char dest[10] = "cats and ";  
   strncat( dest, "dachshunds", 15 );  
   // With secure template overloads enabled (see #define  
   // at top of file), the preceding line is replaced by  
   //    strncat_s( dest, _countof(dest), "dachshunds", 15 );  
   // Instead of causing a buffer overrun, strncat_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncat would  
   // append "dachshunds" and overrun the dest buffer.  
   printf_s( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf_s(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
  **'그'의 4 자를 10 바이트 버퍼를 대상에 추가**  
 **대상의 이전 내용: 'hi '**  
 **대상의 새로운 내용: 'hi ther'**  
**'그'의 5 자를 10 바이트 버퍼를 대상에 추가**  
 **대상의 이전 내용: 'hi '**  
 **대상의 새로운 내용: 'hi there'**  
**'그'의 6 자를 10 바이트 버퍼를 대상에 추가**  
 **대상의 이전 내용: 'hi '**  
 **대상의 새로운 내용: 'hi there'**  
**대상 버퍼가 너무 작습니다.**  
**'그'의 4 자를 10 바이트 버퍼를 대상에 추가**  
 **대상의 이전 내용: 'hello '**  
**잘못 된 매개 변수 처리기를 호출 합니다. \(L "버퍼가 너무 작습니다" && 0\)**  
 **대상의 새로운 내용: "**  
**잘라내기의 예제:**  
**잘림 기능을 사용하여 10 바이트 버퍼 dest에 '존재' 추가**  
 **대상의 이전 내용: 'hello '**  
 **대상의 새로운 내용: 'hello the'**  
 **잘림이 발생 했습니다**  
**잘림 기능을 사용하여 10 바이트 버퍼 dest에 '\!' 추가**  
 **대상의 이전 내용: 'hello '**  
 **대상의 새로운 내용: 'hello \!'**  
 **잘림이 발생하지 않았습니다.**  
**오버 로드 템플릿 보호 예제:**  
**잘못 된 매개 변수 처리기를 호출 합니다. \(L "버퍼가 너무 작습니다" && 0\)**  
 **대상의 새로운 내용: "**   
## 해당 .NET Framework 항목  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
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