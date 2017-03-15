---
title: "_getcwd, _wgetcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wgetcwd"
  - "_getcwd"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd"
  - "wgetcwd"
  - "_wgetcwd"
  - "tgetcwd"
  - "_tgetcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "getcwd 함수"
  - "디렉터리 작업"
  - "_wgetcwd 함수"
  - "_getcwd 함수"
  - "현재 작업 디렉터리"
  - "wgetcwd 함수"
  - "디렉터리 [c + +] 현재 작업"
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _getcwd, _wgetcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 작업 디렉터리를 가져옵니다.  
  
## 구문  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### 매개 변수  
 `buffer`  
 경로의 저장소 위치입니다.  
  
 `maxlen`  
 경로의 최대 길이\(문자 수\)로 `char`의 경우 `_getcwd`자, `wchar_t`의 경우 `_wgetcwd`자입니다.  
  
## 반환 값  
 `buffer`에 대한 포인터를 반환합니다.`NULL` 반환 값은 오류를 나타내고 `errno`는 `ENOMEM`으로 설정되어 `maxlen`바이트를 할당할 메모리가 부족함을 나타내거나\(`NULL` 인수가 `buffer`로 지정된 경우\) `ERANGE`로 설정되어 경로가 `maxlen`자보다 긺을 나타냅니다.`maxlen`이 0보다 작거나 같은 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `_getcwd` 함수는 기본 드라이브에 대한 현재 작업 디렉터리의 전체 경로를 가져오고 `buffer`에 저장합니다. 정수 인수 `maxlen`은 경로의 최대 길이를 지정합니다. 경로의 길이\(null 종결 문자 포함\)가 `maxlen`*을 초과하는 경우 오류가 발생합니다.*`buffer` 인수는 `NULL`일 수 있으며, `maxlen` 크기 이상의 버퍼\(필요한 경우에만\)가 `malloc`를 사용하여 자동으로 할당되어 경로를 저장합니다. 나중에 이 버퍼는 `free`를 호출하고 `_getcwd` 반환 값\(할당된 버퍼에 대한 포인터\)으로 전달하여 해제할 수 있습니다.  
  
 `_getcwd`는 현재 작업 디렉터리의 경로를 나타내는 문자열을 반환합니다. 현재 작업 디렉터리가 루트이면 문자열이 백슬래시\(`\`\)로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리이면 문자열은 백슬래시가 아닌 디렉터리 이름으로 끝납니다.  
  
 `_wgetcwd`은 `_getcwd`의 와이드 문자 버전이고, `buffer` 인수와 `_wgetcwd`의 반환 값은 와이드 문자 문자열입니다. 그렇지 않으면 `_wgetcwd`과 `_getcwd`이 동일하게 작동합니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC`가 정의된 경우 `_getcwd` 및 `_wgetcwd` 호출이 `_getcwd_dbg` 및 `_wgetcwd_dbg` 호출로 대체되어 메모리 할당 디버깅을 허용합니다. 자세한 내용은 [\_getcwd\_dbg, \_wgetcwd\_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)를 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getcwd`|\<direct.h\>|  
|`_wgetcwd`|\<direct.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## 해당 .NET Framework 항목  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)