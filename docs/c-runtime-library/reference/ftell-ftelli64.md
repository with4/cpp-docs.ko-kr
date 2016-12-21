---
title: "ftell, _ftelli64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64"
  - "ftell"
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
  - "_ftelli64"
  - "ftell"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftelli64 함수"
  - "파일 포인터[C++]"
  - "파일 포인터[C++], 현재 위치 가져오기"
  - "ftell 함수"
  - "ftelli64 함수"
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ftell, _ftelli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 포인터의 현재 위치를 가져옵니다.  
  
## 구문  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 대상 `FILE` 구조.  
  
## 반환 값  
 `ftell`및 `_ftelli64` 는 현재 파일 위치를 반환 합니다.  텍스트 모드가 캐리지\-반환 줄바꿈 변환을 발생시키기 때문에 `ftell` 및 `_ftelli64` 가 반환하는 값은 텍스트 모드에서 열린 스트림에 대해 물리적 바이트 오프셋을 나타내지 않습니다.  `fseek` 또는 `_ftelli64` , `_fseeki64` 을 사용하여 `ftell` 로 현재 파일 위치를 반환합니다.  에러 발생시 `ftell`및`_ftelli64` 는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  실행이 계속하도록 혀옹된 경우, 이러한 함수는 \-1L을 반환하고 `errno` 를 ERRNO.H 에 정의된 두개의 상수 중 하나로 설정합니다.  `EBADF` 상수는 `stream` 인수가 유효한 파일 포인터 값이 아니거나 열린 파일을 참조하지 않는 것을 의미합니다.  `EINVAL` 는 잘못된 `stream` 인수가 함수로 전달 되었음을 의미합니다.  찾기 가능한 장치\(터미널 및 프틴터와 같은\) 에서 또는 `stream` 가 열린 파일을 참조하지 않는 경우, 반환 값을 정의되지 않습니다.  
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 `ftell` 및 `_ftelli64` 함수는 `stream` *.* 과 연관된 파일 포인터\(존재하는 경우\)의 현재 위치를 검색합니다. 위치는 스트림의 시작 부분에 상대 오프셋으로서 표현됩니다.  
  
 데이터 추가에 대해 파일을 열때, 현재 파일 위치는 다음 쓰기가 발생할 때가 아닌 마지막 I\/O 작업으로 결정됩니다.  예를 들어, 파일이 추가에 대해 열리고 마지막 작업이 읽기인 경우, 파일 위치는 다음 쓰기 작업이 시작되는 때가 아닌 다음 읽기 작업이 시작될 때 포인트됩니다. \(파일을 추가 용으로 열릴 때, 파일 위치도 이동 되어 쓰기 작업을 수행 하기 전에 파일의 끝이 됩니다.\) 파일이 추가용으로 열리기 전에 I\/O 작업이 없는 경우, 파일 위치는 파일의 시작이 됩니다.  
  
 텍스트 모드에서, CTRL \+ Z는 입력에서의 파일의 마지막 특성으로 해석됩니다.  파일이 읽기\/쓰기 용으로 열린 경우, `fopen` 와 관련된 루틴은 파일의 끝에서 CTRL\+Z 에 대해 확인하고 가능하면 제거합니다.  `ftell` 및 `fseek` 의 결합 또는 `_ftelli64` 및 `_fseeki64` 을 사용하기 때문에 완료 됩니다. CTRL \+ Z로 끝나는 파일 내에서 이동하는 것은 또한 `ftell` 또는 `_ftelli64` 파일의 끝 부분에 부적절하게 행동하는 원인이 될 수 있습니다.  
  
 수행 중에 이 함수는 스레드 호출을 잠그기 때문에 스레드는 안전합니다.  비잠금 버전을 위해 `_ftell_nolock`을 참조하세요.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`ftell`|\<stdio.h\>|\<\<errno.h\>\>|  
|`_ftelli64`|\<stdio.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
  **Position after trying to read 100 bytes: 100**   
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)