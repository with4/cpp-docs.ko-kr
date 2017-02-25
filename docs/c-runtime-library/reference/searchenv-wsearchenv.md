---
title: "_searchenv, _wsearchenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_searchenv"
  - "_wsearchenv"
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
  - "_wsearchenv"
  - "_tsearchenv"
  - "wsearchenv"
  - "_searchenv"
  - "searchenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_searchenv 함수"
  - "_tsearchenv 함수"
  - "_wsearchenv 함수"
  - "환경 경로"
  - "환경 경로, 파일 검색"
  - "파일[C++], 찾기"
  - "searchenv 함수"
  - "tsearchenv 함수"
  - "wsearchenv 함수"
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# _searchenv, _wsearchenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

환경 경로를 사용하여 파일을 검색합니다.  이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [\_searchenv\_s, \_wsearchenv\_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)를 참조하세요.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 `filename`  
 검색할 파일의 이름입니다.  
  
 `varname`  
 검색할 환경입니다.  
  
 `pathname`  
 전체 경로를 저장할 버퍼입니다.  
  
## 설명  
 `_searchenv` 루틴은 지정된 도메인에서 대상 파일을 검색합니다.  `varname` 변수는 디렉터리 경로 목록을 지정하는 모든 환경 변수 또는 사용자 정의 변수\(예: `PATH`, `LIB` 또는 `INCLUDE`\)일 수 있습니다.  `_searchenv`에서 대\/소문자를 구분하므로 `varname`은 환경 변수의 대\/소문자와 일치해야 합니다.  
  
 루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다.  파일을 찾을 수 없는 경우 환경 변수에 지정된 디렉터리에서 찾습니다.  대상 파일이 이러한 디렉터리 중 하나에 있는 경우 새로 만든 경로가 `pathname`에 복사됩니다.  `filename` 파일을 찾을 수 없는 경우 `pathname`에 빈 null 종료 문자열이 포함됩니다.  
  
 `pathname` 버퍼가 생성된 경로 이름의 전체 길이를 수용하려면 `_MAX_PATH`자 이상이어야 합니다.  그렇지 않으면 `_searchenv`가 `pathname` 버퍼를 오버런하여 예기치 않은 동작이 발생할 수 있습니다.  
  
 `_wsearchenv`는 `_searchenv`의 와이드 문자 버전이며, `_wsearchenv`에 대한 인수는 와이드 문자열입니다.  그렇지 않으면 `_wsearchenv`과 `_searchenv`이 동일하게 작동합니다.  
  
 `filename`이 빈 문자열인 경우 이 함수에서 `ENOENT`를 반환합니다.  
  
 `filename` 또는 `pathname`이 `NULL` 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 `errno` 및 오류 코드에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_searchenv`|\<stdlib.h\>|  
|`_wsearchenv`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **CL.EXE의 경로:**  
**C:\\Program Files\\Microsoft Visual Studio 8\\VC\\BIN\\CL.EXE**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_searchenv\_s, \_wsearchenv\_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)