---
title: "fread_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread_s"
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
  - "fread_s"
  - "stdio/fread_s"
dev_langs: 
  - "C++"
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fread_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 데이터를 읽습니다.  이 버전의 [fread](../../c-runtime-library/reference/fread.md) 는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
## 구문  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치  
  
 `bufferSize`  
 파이트에서 원하는 버퍼의 크기입니다.  
  
 `elementSize`  
 바이트에서 읽을 수 있는 항목의 크기입니다.  
  
 `count`  
 읽을 수 있는 항목의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `fread_s` 버퍼로 읽어들인 \(전체\) 항목들의 숫자를 반환하고, 만일 파일의 끝 또는 읽기 오류가 `count` 에 도달되기 전에 발견된 경우, 이것은 `count` 보다 적게 될 수 있습니다.  파일의 끝에 대한 조건으로 오류를 구별하기 위해 `feof` 또는 `ferror` 함수를 사용합니다.  만일 `size` 또는 `count` 가 0인경우, `fread_s` 는 0을 반환하고 버퍼내용은 바뀌지 않습니다.  만일 `stream` 또는 `buffer` 가 null 포인터인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된대로 `fread_s` 가 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
 오류 코드들에 관한 자세한 내용은, [\_doserrno, errno, \_sys\_errlist, 와 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참고하세요.  
  
## 설명  
 `fread_s` 는 입력 `stream` 으로부터 `elementSize` 바이트의 `count` 를 읽고 `buffer` 에 저장합니다.  \(만일 있는 경우\) `stream` 과 연결된 파일 포인터는 실제로 읽은 바이트의 수만큼 증가합니다.  만일 텍스트 모드에서 주어진 스트림이 열린 경우, 캐리지는 반환합니다– 줄 바꿈 쌍은 단일 줄 바꿈 문자로 바뀝니다.  이 교체는 파일 포인터 또는 반환 값에는 영향을 미치지 않습니다.  파일 포인터 위치는 만일 오류가 발생하는 경우 결정되지 않습니다.  부분적으로 읽은 항목의 값은 결정될 수 없습니다.  
  
 이 함수는 다른 스레드를 잠급니다.  만일 비잠금 버전이 필요한 경우, `_fread_nolock`을 사용하세요.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fread_s`|\<stdio.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```cpp  
  
// crt_fread_s.c  
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c  
//  
// This program opens a file that's named FREAD.OUT and  
// writes characters to the file. It then tries to open  
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
#define BUFFERSIZE 30  
#define DATASIZE 22  
#define ELEMENTCOUNT 2  
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)  
#define FILENAME "FREAD.OUT"  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   for ( i = 0; i < DATASIZE; i++ )  
      list[i] = (char)('z' - i);  
   list[DATASIZE] = '\0'; // terminal null so we can print it  
  
   // Open file in text mode:  
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )  
   {  
      // Write DATASIZE characters to stream   
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );  
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );  
      printf( "Wrote %d items\n\n", numwritten );  
      fclose( stream );  
   } else {  
      printf( "Problem opening the file\n" );  
      return -1;  
   }  
  
   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {  
      // Attempt to read in characters in 2 blocks of 11  
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );  
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );  
      printf( "Contents of buffer after write/read:\n\t%s\n", list );  
      fclose( stream );  
   } else {  
      printf( "File could not be opened\n" );  
      return -1;  
   }  
}  
```  
  
  **쓰기\/읽기 전에 버퍼의 내용:**   
 **zyxwvutsrqponmlkjihgfe**  
 **25개 항목을 작성했습니다.**   
 **읽은 11\-바이트 원소들의 수 \= 2**   
 **쓰기\/읽기 후 버퍼의 내용:**   
 **zyxwvutsrqponmlkjihgfe**    
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)