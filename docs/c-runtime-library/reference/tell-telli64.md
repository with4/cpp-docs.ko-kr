---
title: "_tell, _telli64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_telli64"
  - "_tell"
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
  - "tell"
  - "telli64"
  - "_telli64"
  - "_tell"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tell 함수"
  - "_telli64 함수"
  - "파일 포인터[C++]"
  - "파일 포인터[C++], 가져오기"
  - "tell 함수"
  - "telli64 함수"
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _tell, _telli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 포인터의 위치를 가져옵니다.  
  
## 구문  
  
```  
long _tell(  
   int handle  
);  
__int64 _telli64(  
   int handle   
);  
```  
  
#### 매개 변수  
 `handle`  
 열려 있는 파일을 나타내는 파일 설명자입니다.  
  
## 반환 값  
 파일 포인터의 현재 위치입니다.  장치 검색을 할 수 없는 것에 반환 값은 정의 되지 않습니다.  
  
 반환값 \-1L 은 오류를 나타냅니다.  여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `handle` 이 잘못된 파일 기술자인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EBADF` 로 설정하고 \-1L을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 을 참조하십시오.  
  
## 설명  
 `_tell` 함수는 `handle` 인수와 관련 된 파일 포인터\(있는 경우\)의 현재 위치를 가져 옵니다.  위치는 파일의 시작 부분에서 바이트 수로 표시 됩니다.  `_telli64` 함수에 대해, 이 값은 64 비트 정수로 표현 됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_tell`, `_telli64`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_tell.c  
// This program uses _tell to tell the  
// file pointer position after a file read.  
//  
  
#include <io.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <share.h>  
#include <string.h>  
  
int main( void )  
{  
   int  fh;  
   char buffer[500];  
  
   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )  
   {  
      char buff[50];  
      _strerror_s( buff, sizeof(buff), NULL );  
      printf( buff );  
      exit( -1 );  
   }  
  
   if( _read( fh, buffer, 500 ) > 0 )  
      printf( "Current file position is: %d\n", _tell( fh ) );  
   _close( fh );  
}  
```  
  
## Input: crt\_tell.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Current file position is: 20  
```  
  
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)