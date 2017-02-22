---
title: "_umask | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask"
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
  - "_umask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask 함수"
  - "파일 사용 권한[C++]"
  - "파일[C++], 권한 설정"
  - "마스크"
  - "마스크, 파일 권한 설정"
  - "umask 함수"
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _umask
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 파일 권한 마스크를 설정합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_umask\_s](../../c-runtime-library/reference/umask-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### 매개 변수  
 `pmode`  
 기본 사용 권한 설정입니다.  
  
## 반환 값  
 `_umask`는 `pmode`의 이전 값을 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `_umask` 함수는 현재 프로세스의 파일 권한 마스크를 `pmode`에 의해 지정된 모드로 설정합니다*.* 파일 권한 마스크는 `_creat`, `_open`, 또는 `_sopen`에 의해서 만들어진 새 파일의 사용 권한 설정을 수정합니다.  마스크의 비트가 1이면, 파일의 요청된 권한 값의 해당 비트가 0\(허용\)으로 설정됩니다.  해당 비트 마스크의 비트가 0이면 그대로 변경되지 않습니다.  처음으로 파일을 닫을 때까지 새 파일에 대한 사용 권한 설정이 설정되지 않았습니다.  
  
 정수 표현 `pmode`은 SYS\\STAT.H에 정의된 다음의 매니페스트 상수 중 하나 또는 둘 이상을 포함합니다.  
  
 `_S_IWRITE`  
 쓰기에 사용할 수 있습니다.  
  
 `_S_IREAD`  
 읽기에 사용할 수 있습니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기에 사용할 수 있습니다.  
  
 두 상수가 주어지면, 그들은 비트 OR 연산자와 결합됩니다.          `|`  \).  `pmode` 인수가 `_S_IREAD`인 경우, 읽기가 허용되지 않습니다. \(파일은 쓰기 전용\)  `pmode` 인수가 `_S_IWRITE`인 경우, 쓰기가 허용되지 않습니다. \(파일은 읽기 전용\)  예를 들어, 마스크에서 쓰기 비트가 설정되어 있으면 모든 새 파일은 읽기 전용이 됩니다.  MS\-DOS 및 Windows 운영 체제를 사용하여 모든 파일을 읽을 수 있다는 점을 유의하십시오. 쓰기 전용 권한을 부여하는 것이 불가능합니다.  그러므로, 읽기 비트를 `_umask`로 설정하는 것은 파일의 모드에 영향이 없습니다.  
  
 `pmode`은 매니페스트 상수 중 하나의 조합이 아니거나 다른 상수의 대체 집합을 포함합니다. 함수는 단순히 무시됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_umask`|\<io.h\>, \<sys\/stat.h\>, \<sys\/types.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
  **Oldmask \= 0x0000**   
## 해당 .NET Framework 항목  
 [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)