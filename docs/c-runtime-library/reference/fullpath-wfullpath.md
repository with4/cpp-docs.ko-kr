---
title: "_fullpath, _wfullpath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fullpath"
  - "_wfullpath"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wfullpath"
  - "fullpath"
  - "_wfullpath"
  - "_fullpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath 함수"
  - "_wfullpath 함수"
  - "절대 경로"
  - "fullpath 함수"
  - "상대 파일 경로"
  - "wfullpath 함수"
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _fullpath, _wfullpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 상대 경로 이름에 대한 절대 경로나 전체 경로 이름을 만듭니다.  
  
## 구문  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### 매개 변수  
 `absPath`  
 절대 경로나 전체 경로를 포함 하는 버퍼에 대한 포인터 이름 또는 NULL입니다.  
  
 `relPath`  
 상대 경로 이름입니다.  
  
 `maxLength`  
 절대 경로 이름 버퍼의 최대 길이 \(`absPath`\).  `_fullpath` 에 대해 이 길이는 바이트로 표현됩니다. 하지만 `_wfullpath` 에 대해서는 와이드 문자\(`wchar_t`\)입니다.  
  
## 반환 값  
 이 함수의 각각은 절대 경로 이름이 포함 된 버퍼에 대한 포인터를 반환합니다. \(`absPath`\).  오류가 발생 하는 경우 \(예를 들어, `relPath` 로 전달된 값이 잘못되거나 찾을 수 없는 드라이브 문자를 가지는 경우 또는 생성된 절대 경로 이름\(`absPath`\)의 길이가 `maxLength` 보다 큰 경우\) \), 함수는 `NULL` 를 반환합니다.  
  
## 설명  
 `_fullpath` 함수는 `relPath` 에서 정규화된 또는 절대 경로에 대해 상대 경로를 확장하거나 `absPath`*.* 에 이 이름을 저장합니다. `absPath` 가 NULL 인 경우, `malloc` 는 경로 이름을 저장할 충분한 길이의 버퍼를 할당하는데 사용됩니다.  이 버퍼에 대한 해제를 해주어야 합니다.  상대 경로 이름은 현재 위치에서 다른 위치로 경로 지정됩니다.\(현재 작업 디렉터리 예:: "."\).  절대 경로 이름은 루트에서 파일 시스템이 원하는 위치에 도달 하는 데 필요한 전체 경로 나타내는 상대 경로 이름을 확장 합니다.  `_makepath` 와 달리 `_fullpath` 는 이름에 ".\/" 또는 "..\/" 을 포함하는 상대 경로\(`relPath`\) 에 대한 절대 경로의 이름을 얻기 위해 사용 됩니다.  
  
 예를 들어, C 런타임 루틴을 사용 하려면 응용 프로그램 루틴에 대한 선언을 포함 하는 헤더 파일을 포함 해야 합니다.  각 헤더 파일은 문 \(응용 프로그램의 작업 디렉토리에서\) 상대 방식으로 파일의 위치를 ​​참조하는 다음을 포함합니다.  
  
```  
#include <stdlib.h>  
```  
  
 파일의 절대 경로 \(실제의 파일 시스템 위치\)가있을 때 :  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath`  는 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동으로 적절하게 처리 합니다.  `_wfullpath` 는 `_fullpath`의 와이드 문자 버전이며, `_wfullpath` 에 대한 문자열 인수는 와이드 문자 문자열입니다.  `_wfullpath`  와 `_fullpath`  은 `_wfullpath`  가 멀티 바이트 문자의 문자열을 처리하지 않는 것을 제외하고 동일하게 작동합니다.  
  
 `_DEBUG`  및 `_CRTDBG_MAP_ALLOC`  이 정의될 때, `_fullpath` 및 `_wfullpath` 호출은 디버깅 메모리를 허용하는 `_fullpath_dbg` 및 `_wfullpath_dbg` 에 대한 호출로 대체됩니다.  자세한 내용은 [\_fullpath\_dbg, \_wfullpath\_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)를 참조하십시오.  
  
 `maxlen` 가 0보다 작거나 같을 때 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `NULL`을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 `absPath` 버퍼가 `NULL` 인 경우, `_fullpath` 는 [malloc](../../c-runtime-library/reference/malloc.md) 를 호출하여 버퍼를 할당하고 `maxLength` 인수를 무시합니다.  적절하게 버퍼를 해제 해야 합니다. \([free](../../c-runtime-library/reference/free.md) 를 사용하십시오\)  `relPath` 인수가 디스크 드라이브를 지정하는 경우, 이 드라이브의 현재 디렉토리는 경로와 결합됩니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fullpath`|\<stdlib.h\>|  
|`_wfullpath`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
  **Full path is: C:\\Documents and Settings\\user\\My Documents\\test**  
**Full path is: C:\\test**  
**Full path is: C:\\Documents and Settings\\user\\test**   
## 해당 .NET Framework 항목  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)