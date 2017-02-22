---
title: "_umask_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask_s"
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
  - "unmask_s"
  - "_umask_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask_s 함수"
  - "파일 사용 권한[C++]"
  - "파일[C++], 권한 설정"
  - "마스크"
  - "마스크, 파일 권한 설정"
  - "umask_s 함수"
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _umask_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 파일 권한 마스크를 설정합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_umask](../../c-runtime-library/reference/umask.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### 매개 변수  
 \[in\] `mode`  
 기본 사용 권한 설정입니다.  
  
 \[out\] `oldMode`  
 권한 설정의 이전 값입니다.  
  
## 반환 값  
 `Mode`가 유효한 모드를 지정하지 않거나 `pOldMode` 포인터가 `NULL`이면 오류 코드를 반환합니다.  
  
### 오류 조건  
  
|`mode`|`pOldMode`|**반환 값**|`oldMode`의 **내용**입니다.|  
|------------|----------------|--------------|---------------------------|  
|any|`NULL`|`EINVAL`|수정 안 됨|  
|잘못된 모드|any|`EINVAL`|수정 안 됨|  
  
 위의 조건 중 하나가 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `_umask_s` 은 `EINVAL` 를 반환하고, `errno` 에 `EINVAL`를 설정합니다.  
  
## 설명  
 `_umask_s`  함수는 현재 프로세스의 파일 권한 마스크를 `mode`에 의해 지정된 모드로 설정합니다*.* 파일 권한 마스크는 `_creat`, `_open`, 또는 `_sopen`에 의해서 만들어진 새 파일의 사용 권한 설정을 수정합니다.  마스크의 비트가 1이면, 파일의 요청된 권한 값의 해당 비트가 0\(허용\)으로 설정됩니다.  해당 비트 마스크의 비트가 0이면 그대로 변경되지 않습니다.  처음으로 파일을 닫을 때까지 새 파일에 대한 사용 권한 설정이 설정되지 않았습니다.  
  
 정수 표현 `pmode`은 SYS\\STAT.H에 정의된 다음의 매니페스트 상수 중 하나 또는 둘 이상을 포함합니다.  
  
 `_S_IWRITE`  
 쓰기에 사용할 수 있습니다.  
  
 `_S_IREAD`  
 읽기에 사용할 수 있습니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기에 사용할 수 있습니다.  
  
 두 상수가 주어지면, 그들은 비트 OR 연산자와 결합됩니다.          `|`  \).  `mode` 인수가 `_S_IREAD`인 경우, 읽기가 허용되지 않습니다. \(파일은 쓰기 전용\)  `mode` 인수가 `_S_IWRITE`인 경우, 쓰기가 허용되지 않습니다. \(파일은 읽기 전용\)  예를 들어, 마스크에서 쓰기 비트가 설정되어 있으면 모든 새 파일은 읽기 전용이 됩니다.  MS\-DOS 및 Windows 운영 체제를 사용하여 모든 파일을 읽을 수 있다는 점을 유의하십시오. 쓰기 전용 권한을 부여하는 것이 불가능합니다.  그러므로, 읽기 비트를 `_umask_s` 로 설정하는 것은 파일의 모드에 영향이 없습니다.  
  
 `pmode`은 매니페스트 상수 중 하나의 조합이 아니거나 다른 상수의 대체 집합을 포함합니다. 함수는 단순히 무시됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_umask_s`|\<io.h\> 및 \<sys\/stat.h\> 및 \<sys\/types.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
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
 [\_umask](../../c-runtime-library/reference/umask.md)