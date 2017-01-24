---
title: "strcpy_s, wcscpy_s, _mbscpy_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcscpy_s"
  - "_mbscpy_s"
  - "strcpy_s"
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
  - "strcpy_s"
  - "_mbscpy_s"
  - "_tcscpy_s"
  - "wcscpy_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "strcpy_s 함수"
  - "_tcscpy_s 함수"
  - "_mbscpy_s 함수"
  - "문자열 복사"
  - "복사 하는 문자열 [c + +]"
  - "tcscpy_s 함수"
  - "wcscpy_s 함수"
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
caps.latest.revision: 41
caps.handback.revision: 41
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcpy_s, wcscpy_s, _mbscpy_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 복사합니다. 이러한 버전의 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) 에 설명 된 대로 향상 된 보안 기능을 한 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
> [!IMPORTANT]
>  `_mbscpy_s`는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## 구문  
  
```  
errno_t strcpy_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscpy_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscpy_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcpy_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscpy_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscpy_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### 매개 변수  
 `strDestination`  
 대상 문자열 버퍼의 위치입니다.  
  
 `numberOfElements`  
 대상 문자열 버퍼의 크기로, 내로\(narrow\) 함수와 멀티바이트 함수의 경우 `char` 단위이고 와이드\(wide\) 함수의 경우 `wchar_t` 단위입니다.  
  
 `strSource`  
 null 종료 소스 문자열 버퍼입니다.  
  
## 반환 값  
 성공하면 0이고, 실패하면 오류입니다.  
  
### 오류 조건  
  
|`strDestination`|`numberOfElements`|`strSource`|반환 값|`strDestination`의 내용|  
|----------------------|------------------------|-----------------|----------|--------------------------|  
|`NULL`|any|any|`EINVAL`|수정 안 됨|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\]을 0으로 설정합니다.|  
|모두|0 또는 너무 작음|any|`ERANGE`|`strDestination`\[0\]을 0으로 설정합니다.|  
  
## 설명  
 `strcpy_s` 함수는 null 종결 문자를 포함하여 `strSource`의 주소 내용을 `strDestination`에서 지정하는 위치로 복사합니다. 대상 문자열은 소스 문자열 및 이 문자열의 null 종결 문자를 포함할 만큼 충분히 커야 합니다. 소스 문자열과 대상 문자열이 겹치는 경우 `strcpy_s`의 동작이 정의되지 않습니다.  
  
 `wcscpy_s`는 와이드 문자 버전의 `strcpy_s`이고, `_mbscpy_s`는 멀티바이트 문자 버전입니다.`wcscpy_s`의 인수 및 반환 값은 와이드 문자열이며 `_mbscpy_s`의 인수와 반환 값은 멀티바이트 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 경우 `strDestination` 또는 `strSource` null 포인터가 하거나에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 대상 문자열이 너무 작으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우, 이러한 함수는 `EINVAL`을 반환하고 `errno`를 `EINVAL`로 설정\(`strDestination` 또는 `strSource`가 null 포인터일 때\)하며 `ERANGE`를 반환하고 `errno`를 `ERANGE`로 설정\(대상 문자열이 너무 작을 때\)합니다.  
  
 실행이 완료되면 대상 문자열은 항상 null로 종료됩니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없음\), 보안 수준이 낮은 기존 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFE로 버퍼를 채웁니다. 사용 하 여이 동작을 사용 하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscpy_s`|`strcpy_s`|`_mbscpy_s`|`wcscpy_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strcpy_s`|\<string.h\>|  
|`wcscpy_s`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbscpy_s`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 예제  
  
```  
// crt_strcpy_s.cpp  
// This program uses strcpy_s and strcat_s  
// to build a phrase.  
//  
  
#include <string.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   char string[80];  
   // using template versions of strcpy_s and strcat_s:  
   strcpy_s( string, "Hello world from " );  
   strcat_s( string, "strcpy_s " );  
   strcat_s( string, "and " );  
   // of course we can supply the size explicitly if we want to:  
   strcat_s( string, _countof(string), "strcat_s!" );  
  
   printf( "String = %s\n", string );  
}  
```  
  
```Output  
문자열 = Hello world from strcpy_s and strcat_s!  
```  
  
## 해당 .NET Framework 항목  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)