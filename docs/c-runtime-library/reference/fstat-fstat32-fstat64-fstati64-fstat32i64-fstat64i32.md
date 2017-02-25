---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fstat32"
  - "_fstat64"
  - "_fstati64"
  - "_fstat"
  - "_fstat64i32"
  - "_fstat32i64"
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
  - "_fstat32i64"
  - "fstat"
  - "fstat64i32"
  - "_fstat64"
  - "_fstati64"
  - "fstat64"
  - "_fstat32"
  - "fstat32i64"
  - "fstati64"
  - "_fstat"
  - "fstat32"
  - "_fstat64i32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstat64 함수"
  - "fstati64 함수"
  - "_fstat64i32 함수"
  - "_fstat32i64 함수"
  - "_fstat32 함수"
  - "파일 정보"
  - "fstat64i32 함수"
  - "fstat32 함수"
  - "fstat 함수"
  - "fstat64 함수"
  - "_fstat 함수"
  - "_fstati64 함수"
  - "fstat32i64 함수"
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열려 있는 파일에 대 한 정보를 가져옵니다.  
  
## 구문  
  
```  
int _fstat(   
   int fd,  
   struct _stat *buffer   
);  
int _fstat32(   
   int fd,  
   struct __stat32 *buffer   
);  
int _fstat64(   
   int fd,  
   struct __stat64 *buffer   
);  
int _fstati64(   
   int fd,  
   struct _stati64 *buffer   
);  
int _fstat32i64(   
   int fd,  
   struct _stat32i64 *buffer   
);  
int _fstat64i32(   
   int fd,  
   struct _stat64i32 *buffer   
);  
```  
  
#### 매개 변수  
 `fd`  
 열린 파일의 파일 설명자입니다.  
  
 `buffer`  
 결과를 저장할 구조에 대 한 포인터입니다.  
  
## 반환 값  
 파일 상태 정보를 가져오는 경우 0을 반환 합니다. 반환 값 –1은 오류를 나타냅니다. 파일 설명자가 잘못 된 경우 또는 `buffer` 는 `NULL`, 를에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 `errno` 로 설정 된 `EBADF`, 잘못 된 파일 설명자를의 경우 또는 `EINVAL`, 경우 `buffer` 는 `NULL`합니다.  
  
## 설명  
 `_fstat` 함수에 연결 된 열려 있는 파일에 대 한 정보를 가져오는 데 `fd` 가리키는 구조에 저장 하 고 `buffer`합니다.`_stat` SYS\\Stat.h에 정의 된 구조에는 다음 필드가 포함 됩니다.  
  
 `st_atime`  
 마지막 파일 액세스 시간입니다.  
  
 `st_ctime`  
 파일의 생성의 시간입니다.  
  
 `st_dev`  
 경우 장치를 `fd`그렇지 않으면 0입니다.  
  
 `st_mode`  
 파일 모드 정보의 비트 마스크입니다.`_S_IFCHR` 비트가 경우 `fd` 장치를 참조 합니다.`_S_IFREG` 비트가 경우 `fd` 일반 파일을 가리킵니다. 읽기\/쓰기 비트는 파일의 사용 권한 모드에 따라 설정 됩니다.`_S_IFCHR` 및 다른 상수 SYS\\Stat.h에 정의 됩니다.  
  
 `st_mtime`  
 파일의 마지막 수정 시간입니다.  
  
 `st_nlink`  
 NTFS가 아닌 파일 시스템에서 항상 1입니다.  
  
 `st_rdev`  
 경우 장치를 `fd`그렇지 않으면 0입니다.  
  
 `st_size`  
 크기 \(바이트\)에서 파일입니다.  
  
 경우 `fd` 을 장치에 대 한 참조는 `st_atime`, `st_ctime`, `st_mtime`, 및 `st_size` 필드는 의미가 없습니다.  
  
 Stat.h 사용 하기 때문에 [\_dev\_t](../../c-runtime-library/standard-types.md) 입력 Types.h에 정의 된를 포함 해야 합니다 Types.h Stat.h 하기 전에 코드에서.  
  
 `_fstat64`, 를 사용 하는 `__stat64` 파일 작성 날짜 23시 59분: 59 까지의 3000 년 12 월 31 일 UTC 표현할 수를 허용 하는 다른 함수만 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타내는 반면, 구조입니다. 자정 1970 년 1 월 1 일에 이러한 모든 함수에 대 한 날짜 범위의 하한값입니다.  
  
 이러한 함수의 변형 32 비트 또는 64 비트 시간 형식 및 32 비트 또는 64 비트 파일 길이 지원합니다. 첫 번째 숫자 접미사\(`32` 또는 `64`\)는 사용된 시간 형식의 크기를 나타내며, 두 번째 접미사\(`i32` 또는 `i64`\)는 파일 크기가 32비트 정수로 표시되는지 아니면 64비트 정수로 표시되는지를 나타냅니다.  
  
 `_fstat` 에 해당 `_fstat64i32`, 및 `struct``_stat` 64 비트 시간을 포함 합니다. 그렇습니다 하지 않는 한 `_USE_32BIT_TIME_T` 이 있는 경우 이전 동작이 적용; 정의 된 `_fstat` 는 32 비트 시간을 사용 하 고 `struct``_stat` 32 비트 시간을 포함 합니다. 같은 기준이 `_fstati64`합니다.  
  
### \_stat의 시간 형식 및 파일 길이 형식 변형  
  
|함수|\_USE\_32BIT\_TIME\_T 정의 여부|시간 형식|파일 길이 형식|  
|--------|---------------------------------|-----------|--------------|  
|`_fstat`|정의되지 않음|64비트|32비트|  
|`_fstat`|정의됨|32비트|32비트|  
|`_fstat32`|매크로 정의의 영향을 받지 않음|32비트|32비트|  
|`_fstat64`|매크로 정의의 영향을 받지 않음|64비트|64비트|  
|`_fstati64`|정의되지 않음|64비트|64비트|  
|`_fstati64`|정의됨|32비트|64비트|  
|`_fstat32i64`|매크로 정의의 영향을 받지 않음|32비트|64비트|  
|`_fstat64i32`|매크로 정의의 영향을 받지 않음|64비트|32비트|  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`_fstat`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
|`_fstat32`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
|`_fstat64`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
|`_fstati64`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
|`_fstat32i64`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
|`_fstat64i32`|\< sys\/stat.h \> 및 \< sys\/types.h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_fstat.c  
// This program uses _fstat to report  
// the size of a file named F_STAT.OUT.  
  
#include <io.h>  
#include <fcntl.h>  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <errno.h>  
#include <share.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int fd, result;  
   char buffer[] = "A line to output";  
   char timebuf[26];  
   errno_t err;  
  
   _sopen_s( &fd,  
             "f_stat.out",  
             _O_CREAT | _O_WRONLY | _O_TRUNC,  
             _SH_DENYNO,  
             _S_IREAD | _S_IWRITE );  
   if( fd != -1 )  
      _write( fd, buffer, strlen( buffer ) );  
  
   // Get data associated with "fd":   
   result = _fstat( fd, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      if (errno == EBADF)  
        printf( "Bad file descriptor.\n" );  
      else if (errno == EINVAL)  
        printf( "Invalid argument to _fstat.\n" );  
   }  
   else  
   {  
      printf( "File size     : %ld\n", buf.st_size );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid argument to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
   _close( fd );  
}  
```  
  
```Output  
파일 크기: 수정 하는 16 시간: 월 7 일 수요일 15시 25분: 11 2003  
```  
  
## 해당 .NET Framework 항목  
 적용할 수 없음 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)