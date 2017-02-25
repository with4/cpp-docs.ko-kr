---
title: "_searchenv_s, _wsearchenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsearchenv_s"
  - "_searchenv_s"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_searchenv_s"
  - "_wsearchenv_s"
  - "wsearchenv_s"
  - "searchenv_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_searchenv_s 함수"
  - "_tsearchenv_s 함수"
  - "_wsearchenv_s 함수"
  - "버퍼 오버런"
  - "버퍼[C++], 오버런 방지"
  - "버퍼[C++], 버퍼 오버런"
  - "환경 경로"
  - "환경 경로, 파일 검색"
  - "파일[C++], 찾기"
  - "searchenv_s 함수"
  - "tsearchenv_s 함수"
  - "wsearchenv_s 함수"
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# _searchenv_s, _wsearchenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

환경 경로를 사용하여 파일을 검색 합니다.  이러한 버전의 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) 는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 \[in\] `filename`  
 검색할 리소스의 이름입니다.  
  
 \[in\] `varname`  
 검색 하는 환경입니다.  
  
 \[out\] `pathname`  
 전체 경로 저장 하는 버퍼입니다.  
  
 \[in\] `numberOfElements`  
 `pathname` 버터의 크기입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
 `filename` 을 `ENOENT`로 설정하면 빈 문자열\(""\)이 반환됩니다.  
  
### 오류 조건  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|반환 값|`pathname`의 내용입니다.|  
|----------------|---------------|----------------|------------------------|----------|------------------------|  
|any|any|`NULL`|any|`EINVAL`|해당 없음|  
|`NULL`|any|any|any|`EINVAL`|변경 되지 않음|  
|any|any|any|\<\= 0|`EINVAL`|변경 되지 않음|  
  
 이러한 오류 조건이 발생 하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못 된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `_searchenv_s` 지정된 도메인의 대상 파일에대한 정기적인 검색을 합니다.  `varname` 변수는 환경 또는 사용자 정의 변수같은 디렉터리 경로의 목록을 지정 하는 `PATH`, `LIB`, 및 `INCLUDE` 등 이와 같은 변수입니다.  `_searchenv_s` 대\/소문자 구분을 해야하기 때문에, `varname` 환경 변수는 대\/소문자와 일치 해야 합니다.  `varname` 는 프로세스의 환경에서 정의된 환경 변수 이름 일치 하지 않으면, 0을 반환 하는 함수이고 `pathname` 변수는 변경 되지 않습니다.  
  
 현재 작업 디렉터리에 있는 파일에 대한 루틴을 먼저 검색합니다.  파일을 찾지 못하면 다음 환경 변수에서 지정한 디렉터리를 찾습니다.  대상 파일이 해당 디렉터리인 경우, `pathname` 에 새로 생성된 된 경로에 복사합니다.  `filename` 파일을 찾을 수 없을 경우, `pathname` 빈 null로 끝나는 문자열을 포함 합니다.  
  
 `pathname` 버터는 적어도 생성된 경로 이름의 전체 길이가 맞는 `_MAX_PATH` 문자입니다.  그렇지 않으면 `_searchenv_s` 는 예기치 않은 동작이 발생한 `pathname` 버퍼를 초과실행할수도 있습니다.  
  
 `_wsearchenv_s`는 `_searchenv_s`의 와이드 문자 버전이며, `_wsearchenv_s`에 대한 인수는 와이드 문자 문자열입니다.  `_wsearchenv_s` 및 `_searchenv_s` 는 동일하게 작동합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_searchenv_s`|\<stdlib.h\>|  
|`_wsearchenv_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **CL에 대 한 경로입니다.EXE:**  
**drive letter:\\Program Files\\Microsoft Visual Studio 11.0\\VC**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)