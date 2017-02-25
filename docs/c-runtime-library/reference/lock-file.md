---
title: "_lock_file | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lock_file"
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
  - "_lock_file"
  - "lock_file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lock_file 함수"
  - "파일 잠금[C++]"
  - "lock_file 함수"
ms.assetid: 75c7e0e6-efff-4747-b6ed-9bcf2b0894c3
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _lock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`FILE` 개체에 동시에 액세스하는 스레드들로부터 일관성을 보장하기 위해 `FILE` 개체를 잠급니다.  
  
## 구문  
  
```  
void _lock_file(  
   FILE* file  
);  
```  
  
#### 매개 변수  
 `file`  
 파일 처리기입니다.  
  
## 설명  
 `_lock_file` 함수는 `file`에 의해 지정된 `FILE` 개체를 잠급니다.  내부 파일은 `_lock_file`에 의해 잠기지 않습니다.  파일에 대한 잠금을 해제하기 위하여 [\_unlock\_file](../../c-runtime-library/reference/unlock-file.md)를 사용합니다.  `_lock_file` 및 `_unlock_file`의 호출은 반드시 스레드에서 일치해야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lock_file`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_lock_file.c  
// This example creates multiple threads that write to standard output  
// concurrently, first with _file_lock, then without.  
  
#include <stdio.h>  
#include <process.h>// _beginthread  
#include <windows.h>// HANDLE  
  
void Task_locked( void* str )  
{  
    for( int i=0; i<1000; ++i )  
    {  
        _lock_file( stdout );  
        for( char* cp = (char*)str; *cp; ++cp )  
        {  
            _fputc_nolock( *cp, stdout );  
        }  
        _unlock_file( stdout );  
    }  
}  
  
void Task_unlocked( void* str )  
{  
    for( int i=0; i<1000; ++i )  
    {  
        for( char* cp = (char*)str; *cp; ++cp )  
        {  
            fputc( *cp, stdout );  
        }  
    }  
}  
  
int main()  
{  
    HANDLE h[3];  
    h[0] = (HANDLE)_beginthread( &Task_locked, 0, "First\n" );  
    h[1] = (HANDLE)_beginthread( &Task_locked, 0, "Second\n" );  
    h[2] = (HANDLE)_beginthread( &Task_locked, 0, "Third\n" );  
  
    WaitForMultipleObjects( 3, h, true, INFINITE );  
  
    h[0] = (HANDLE)_beginthread( &Task_unlocked, 0, "First\n" );  
    h[1] = (HANDLE)_beginthread( &Task_unlocked, 0, "Second\n" );  
    h[2] = (HANDLE)_beginthread( &Task_unlocked, 0, "Third\n" );  
  
    WaitForMultipleObjects( 3, h, true, INFINITE );  
}  
```  
  
  **...**  
**첫 번째**  
**초**  
**첫 번째**  
**초**  
**Third**  
**초**  
**Third**  
**초**  
**...**  
**FSiercsotn**  
**dF**  
**iSrescto**  
**nFdi**  
**rSsetc**  
**oFnidr**  
**sSte**  
**cFoinrds**  
**tS**  
**eFciornsdt**   
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_unlock\_file](../../c-runtime-library/reference/unlock-file.md)