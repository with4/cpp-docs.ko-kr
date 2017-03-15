---
title: "_locking | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_locking"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_locking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_locking 함수"
  - "바이트[C++], 파일 잠금"
  - "파일[C++], 잠금"
  - "파일[C++], 바이트 잠금"
  - "locking 함수"
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _locking
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잠그거나 잠금을 해제할 파일의 바이트.  
  
## 구문  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### 매개 변수  
 `fd`  
 파일 설명자  
  
 *mode*  
 수행할 잠금 작업  
  
 *nbytes*  
 잠글 바이트 수입니다.  
  
## 반환 값  
 성공하면 `_locking` 는 0을 반환합니다.  [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 가 다음의 값 중 하나로 설정 되는 경우 반환 값 \-1은 오류를 나타냅니다.  
  
 `EACCES`  
 잠금 위반 \(파일이 이미 잠금 또는 잠금 해제된 경우\).  
  
 `EBADF`  
 잘못 된 파일 설명자입니다.  
  
 `EDEADLOCK`  
 잠금 위반이 발생 했습니다.  `_LK_LOCK` 또는 `_LK_RLCK` 플래그가 지정되고 파일이 10번의 시도 후에도 잠기지 않는 경우 반환 됩니다.  
  
 `EINVAL`  
 잘못 된 매개 변수가 `_locking` 에 제공됩니다.  
  
 오류가 잘못된 파일 설명자와 같은 잘못 된 매개 변수에 의해 발생한 경우, 잘못된 매개 변수 처리기가 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 호출됩니다.  
  
## 설명  
 `_locking` 함수는 파일의 `fd` 에 의해 지정된 *nbytes* 바이트를 잠그거나 잠금 해제 합니다.  파일 내의 바이트를 잠그는 것은 다른 프로세스에 의해 액세스 되는 것을 막습니다.  모든 잠금 또는 잠금 해제는 파일 포인터의 현재 위치에서 시작 하고 다음 *nbytes* 바이트로 진행됩니다.  파일의 이전 바이트를 잠그는 것도 가능합니다.  
  
 *모드* 는 Locking.h에 정의 된 다음 매니페스트 상수 중 하나 여야 합니다.  
  
 `_LK_LOCK`  
 지정된 바이트를 잠급니다.  바이트를 잠글 수 없으면, 프로그램이 바로 1 초 후에 다시 시도 합니다.  10 번 시도 후에도 바이트를 잠글 수 없는 경우, 상수는 오류를 반환 합니다.  
  
 `_LK_NBLCK`  
 지정된 바이트를 잠급니다.  바이트를 잠글 수 없는 경우, 상수는 오류를 반환 합니다.  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK`와 동일합니다.  
  
 `_LK_RLCK`  
 `_LK_LOCK`와 동일합니다.  
  
 `_LK_UNLCK`  
 지정된 바이트를 잠금 해제하려면 반드시 이전에 잠금이 되어 있어야 합니다.  
  
 오버랩 되지 않는 여러 파일의 영역을 잠글 수 있습니다.  잠금이 해제 되는 영역은 이전에 잠겨 있어야 합니다.  `_locking` 는 인접한 지역을 병합하지 않습니다. 두 개의 영역이 인접한 경우, 각 영역은 별도로 잠금 해제 되어야 합니다.  지역은 간단하게 잠금되어야 하며 파일을 닫거나 프로그램을 종료하기 전에 잠금을 해제 해야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_locking`|\<io.h\> 및 \<sys\/locking.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## Input: crt\_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## 샘플 출력  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)