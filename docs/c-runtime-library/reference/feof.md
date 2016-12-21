---
title: "feof | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feof"
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
  - "feof"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "파일의 끝, 테스트"
  - "feof 함수"
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 파일의 끝에 대한 테스트입니다.  
  
## 구문  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `feof` 함수는읽기 작업이 파일의 이전 부분을 읽으면 0이 아닌 값을 반환하고 그렇지 않으면 0을 반환합니다.  스트림 포인터가 `NULL` 인 경우, 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정 되고 `feof` 는 0을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `feof` 루틴\(함수 및 매크로로 구현\)은 전달 된 `stream` 의 끝 여부를 결정합니다.  파일의 끝이 전달 되면, 읽기 작업은 스트림이 닫힐 때까지 때까지 또는 `rewind`, `fsetpos`, `fseek`, 또는 `clearerr` 가 반대로 호출 되기 전까지 파일의 끝 지시자를 반환합니다.  
  
 예를 들어, 10 바이트 파일에서 10 바이트를 읽을 경우파일의 끝에 파일 포인터가 있어도 `feof`  는 끝을 넘어 읽을 수 없으므로 0을 반환합니다.  11 바이트를 읽으려고 시도한 경우에만 `feof` 는 0이 아닌 값을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`feof`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## Input: crt\_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Number of bytes read = 19  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)