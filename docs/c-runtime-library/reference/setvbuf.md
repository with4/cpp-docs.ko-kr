---
title: "setvbuf | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setvbuf"
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
  - "setvbuf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "스트림 버퍼링 제어"
  - "setvbuf 함수"
  - "스트림 버퍼링"
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림 버퍼링 및 버퍼 크기를 제어합니다.  
  
## 구문  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `buffer`  
 사용자가 할당 한 버퍼입니다.  
  
 `mode`  
 버퍼링 모드입니다.  
  
 `size`  
 버퍼 크기\(바이트\)입니다.  허용 범위: 2 \<\= `size` \<\= INT\_MAX \(2147483647\).  내부적으로 `size`에 제공되는 값은 가장 가까운 2의 배수로 내림됩니다.  
  
## 반환 값  
 성공하면 0를 반환합니다.  
  
 `stream`이 `NULL`이거나 `mode` 또는 `size`가 유효한 변경 이내에 있지 않은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속 실행하는 것이 허용된 경우, 이 함수는 \-1을 반환하고 `errno`을 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `setvbuf` 함수는 프로그램이 버퍼링과 `stream`의 버퍼 크기를 제어하도록 허용합니다.  `stream`는 반드시 열린 이래로 I\/O 작업의 영향을 받지 않은 열린 파일을 참조해야 합니다.  `NULL`이 아닌 경우, 즉 `setvbuf`가 `size`\/2 \* 2 바이트 길이의 자동으로 할당된 버퍼를 사용하는 경우 `buffer`에 의해 가리켜지는 배열은 버퍼로 사용됩니다.  
  
 모드는 `_IOFBF`, `_IOLBF` 또는 `_IONBF`이어야 합니다.  `mode`가 `_IOFBF` 또는 `_IOLBF`이면, `size`이 버퍼의 크기로 사용됩니다.  `mode`가 `_IONBF`이면, 스트림은 버퍼가 해제되고 `size` 및 `buffer`는 무시됩니다.  `mode`의 값 및 그 의미는 다음과 같습니다.  
  
 `_IOFBF`  
 완전 버퍼링입니다. 즉, `buffer`이 버퍼로 사용되고 `size`가 버퍼의 크기로 사용됩니다.  `buffer`가 `NULL`이면, `size` 바이트의 길이의 자동으로 할당된 된 버퍼가 사용됩니다.  
  
 `_IOLBF`  
 일부 시스템에서 이것은 선형 버퍼링을 제공합니다.  그러나, Win32에서 동작은 `_IOFBF` \- 전체 버퍼링과 동일합니다.  
  
 `_IONBF`  
 `buffer` 또는 `size`에 관계없이 버퍼가 사용되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`setvbuf`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **'stream1' now has a buffer of 1024 bytes**  
**'stream2' now has no buffer**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)