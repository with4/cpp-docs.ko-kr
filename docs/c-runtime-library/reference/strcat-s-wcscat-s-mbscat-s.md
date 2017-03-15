---
title: "strcat_s, wcscat_s, _mbscat_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strcat_s"
  - "_mbscat_s"
  - "wcscat_s"
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
  - "strcat_s"
  - "wcscat_s"
  - "_mbscat_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbscat_s 함수"
  - "문자열 추가"
  - "mbscat_s 함수"
  - "strcat_s 함수"
  - "문자열[C++], 추가"
  - "wcscat_s 함수"
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# strcat_s, wcscat_s, _mbscat_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 추가 합니다.  이러한 버전의 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  `_mbscat_s` 는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t strcat_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscat_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscat_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcat_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscat_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscat_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### 매개 변수  
 `strDestination`  
 Null 종료 수신지 문자열 버퍼입니다.  
  
 `numberOfElements`  
 대상 문자열 버퍼의 크기입니다.  
  
 `strSource`  
 Null 종료 소스 문자열 버퍼입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`strDestination`|`numberOfElements`|`strSource`|반환 값|`strDestination`의 내용입니다.|  
|----------------------|------------------------|-----------------|----------|------------------------------|  
|`NULL` 나 종료 되지 않은|any|any|`EINVAL`|수정 안 됨|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\]을 0으로 설정합니다.|  
|any|0 또는 너무 작습니다.|any|`ERANGE`|`strDestination`\[0\]을 0으로 설정합니다.|  
  
## 설명  
 `strcat_s` 함수는 `strSource` 를 `strDestination` 에 추가하고 null 문자로 결과 문자열을 종료 합니다.  `strSource` 의 시작 문자는 `strDestination`의 null 종결 문자를 덮어씁니다.  원본 영역과 대상 문자열이 겹치면 `strcat_s` 동작이 지정되지 않습니다.  
  
 참고 두 번째 매개 변수는 버퍼 크기가 아니라 남은의 전체 크기:  
  
```  
char buf[16];  
strcpy_s(buf, 16, "Start");  
strcat_s(buf, 16, " End");               // Correct  
strcat_s(buf, 16 – strlen(buf), " End"); // Incorrect  
```  
  
 `wcscat_s` 및 `_mbscat_s` 는 와이드 문자 및 `strcat_s`의 멀티 바이트 문자 버전입니다.  `wcscat_s`의 인수 및 반환 값은 와이드 문자열이며, `_mbscat_s`는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 만약 `strDestination` 가 null 포인터이거나 null로 끝나는 경우 `strSource` 가 `NULL` 포인터이거나 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md).에 설명된 대로 대상 문자열은 너무 작은 경우 잘못 된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EINVAL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscat_s`|`strcat_s`|`_mbscat_s`|`wcscat_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strcat_s`|\<string.h\>|  
|`wcscat_s`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbscat_s`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)에 있는 코드 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)