---
title: "setbuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setbuf"
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
  - "setbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "setbuf 함수"
  - "스트림 버퍼링"
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# setbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤 스트림 버퍼링  이 함수는 사용 되지 않습니다. 대신 [setvbuf](../../c-runtime-library/reference/setvbuf.md) 을 사용 하십시오.  
  
## 구문  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `buffer`  
 사용자가 할당 한 버퍼입니다.  
  
## 설명  
 `setbuf` 함수는 `stream` 에 대한 버퍼링을 컨트롤 합니다.  `stream` 인수는 반드시 읽기 또는 쓰기되지 않는 열려있는 파일을 참조 해야 합니다.  `buffer` 인수가 `NULL` 인 경우, 스트림은 버퍼 되지 않습니다.  그렇지 않다면, 버퍼는 길이 `BUFSIZ` 의 문자 배열을 가르켜야 합니다. `BUFSIZ` 는 STDIO.H에 정의된 버퍼 사이즈 입니다.  지정 된 스트림에 대한 기본 시스템에서 할당 된 버퍼 대신 사용자가 지정한 버퍼 출력을 위해 사용 하는 버퍼링입니다.  `stderr` 스트림은 기본적으로 버퍼 되지 않습니다. 하지만 `stderr` 에 버퍼를 할당 하기 위해 `setbuf` 를 사용할 수 있습니다.  
  
 `setbuf` 는 [setvbuf](../../c-runtime-library/reference/setvbuf.md) 에 의해 대체 됩니다. 이것은 새로운 코드에 대해 선호되는 루틴입니다.  `setbuf` 는 기존 코드와의 호환성을 위해 유지 됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`setbuf`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **stream1 set to user\-defined buffer at: 0012FCDC**  
**stream2 buffering disabled**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)