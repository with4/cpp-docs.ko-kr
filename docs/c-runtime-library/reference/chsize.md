---
title: "_chsize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chsize"
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
  - "_chsize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chsize 함수"
  - "chsize 함수"
  - "파일[C++], 크기 변경"
  - "크기"
  - "크기, 파일 변경"
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chsize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 크기를 수정합니다.  보다 안전한 버전을 이용하기 위해; [\_chsize\_s](../../c-runtime-library/reference/chsize-s.md)을 참고하세요.  
  
## 구문  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 설명자입니다.  
  
 `size`  
 새 파일의 길이\(바이트\)입니다.  
  
## 반환 값  
 만일 파일의 크기가 성공적으로 변경되면, `_chsize` 은 0을 반환합니다.  오류는 \-1의 반환값을 나타냅니다; 지정된 파일이 접근에 대하여 허가되지 않은 경우, `errno` 는 `EACCES` 로, 지정된 파일이 읽기전용이거나 설명자가 잘못된 경우 `EBADF` 로, 장치에 공간이 없는 경우 `ENOSPC` `size` 가 0보다 작은 경우 `EINVAL`로 설정됩니다.  
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 `_chsize` 함수는 `size` 로 지정된 길이로 `fd` 를 사용하여 파일을 자르거나 확장합니다.  파일은 쓰기를 허용 하는 모드에서 열려 있어야 합니다.  파일이 확장되는 경우, null 문자\('\\0'\)이 추가됩니다.  파일이 잘린경우, 파일의 본래 길이로 단축된 파일의 끝으로부터 모든 데이터가 손실됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만일 `size` 0보다 더 작거나 `fd` 이 잘못된 파일 설명자인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서처럼 잘못된 매개변수 처리기가 호출됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_chsize`|\<io.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
  **이전의 파일 길이: 0**  
**성공적으로 변경된 크기**  
**이후 파일 길이: 329678**   
## 해당 .NET Framework 항목  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)