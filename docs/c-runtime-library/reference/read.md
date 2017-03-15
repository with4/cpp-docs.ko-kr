---
title: "_read | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_read"
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
  - "_read"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_read 함수"
  - "데이터[C++], 읽기"
  - "데이터[CRT]"
  - "파일[C++], 읽기"
  - "read 함수"
  - "데이터 읽기[C++]"
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _read
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일에서 데이터를 읽습니다.  
  
## 구문  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 기술자입니다.  
  
 *buffer*  
 출력을 위한 저장소 위치  
  
 *count*  
 최대 바이트 수입니다.  
  
## 반환 값  
 \_**read** 는 읽은 바이트의 수를 반환합니다. 이 값은 파일에 남겨진 *count* 바이트보다 적은 경우, 또는 파일이 각 캐리지 반환 줄 피드\(CRLF\) 쌍이 단일 줄 피드 문자로 대체되는 텍스트 모드로 열린 경우 *count* 보다 작을 수 있습니다.  단일 줄 바꿈 문자만 반환 값에서 계산 됩니다.  대체 파일 포인터는 변경 되지 않습니다.  
  
 함수는 파일의 끝을 읽는 경우 0을 반환 합니다.  `fd` 가 잘못된 경우, 파일은 읽기에 대해 열리지 않고, 파일이 잠긴 경우, 잘못된 매개 변수 처리기가 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 호출 됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 을 `EBADF` 로 설정합니다.  
  
 *buffer* 가 **NULL** 인 경우, 잘못된 매개 변수 처리기가 호출 됩니다.  계속해도 실행하도록 혀용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL` 로 설정합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_read` 함수는 `fd` 와 관련된 파일에서 *buffer* 의 *count* 의 최대를 읽습니다.  지정 된 파일과 연결 된 파일 포인터의 현재 위치에서 읽기 작업을 시작 합니다.  읽기 작업을 한 후 파일 포인터는 다음 읽지 않은 문자를 가리킵니다.  
  
 파일이 텍스트 모드에서 열린 경우, 읽기는 `_read` 가 파일의 끝을 나타내는 CTRL\+Z 문자를 만나면 종료됩니다.  [\_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) 를 사용하여 파일의 끝 표시기를 없앱니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_read`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## Input: crt\_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## Output  
  
```  
Read 19 bytes from file  
```  
  
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_write](../../c-runtime-library/reference/write.md)