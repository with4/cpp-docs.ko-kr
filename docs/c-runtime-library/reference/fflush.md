---
title: "fflush | Microsoft Docs"
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
  - "fflush"
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
  - "fflush"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fflush 함수"
  - "플러시"
  - "스트림, 플러시"
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fflush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림을 비웁니다.  
  
## 구문  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 버퍼가 성공적으로 비워진 경우, `fflush`는 0을 반환합니다.  지정된 스트림이 버퍼가 없거나 읽기 전용으로 열려있는 경우에도 값 0이 반환됩니다.  반환값 `EOF`은 오류를 나타냅니다.  
  
> [!NOTE]
>  `fflush`가 `EOF`를 반환했을 경우, 데이터가 쓰기 오류 때문에 손실되었을 수 있습니다.  임계 오류 처리기를 설정할 때, `setvbuf` 함수로 버퍼링을 끄거나 스트림 I\/O 함수 대신 `_open`, `_close` 및 `_write`과 같은 낮은 레벨의 I\/O 루틴을 사용하는 것이 가장 안전합니다.  
  
## 설명  
 `fflush` 함수는 스트림을 비웁니다.  `stream`와 연결된 파일이 출력을 위해 열렸다면, `fflush`는 해당 파일에 스트림과 연결된 버퍼의 내용을 씁니다.  스트림이 출력을 위해 열렸다면, `fflush`는 버퍼의 내용을 지웁니다.  `fflush`는 `stream`과 반대되는 모든 `ungetc`으로의 호출을 무효화합니다.  또한 `fflush(NULL)`는 모든 열린 출력 스트림을 비웁니다.  호출 후 스트림은 계속 열려 있습니다.  `fflush`는 버퍼되지 않은 스트림에 효과가 없습니다.  
  
 버퍼는 보통 자동으로 디스크에 데이터를 쓸 수 있는 최적의 시간을 결정하는 운영체제에서 정상적으로 유지됩니다. 버퍼가 꽉 찼을 때, 스트림을 닫을 때 또는 프로그램이 정상적으로 스트림을 닫지 않고 종료될 때입니다.  런타임 라이브러리의 디스크에 커밋 기능을 통해 중요한 데이터가 운영체제 버퍼 대신 디스크에 직접 작성되었는지 확인할 수 있습니다.  기존 프로그램을 다시 작성하지 않고도 Commode.obj에 프로그램의 개체 파일을 연결하여 이 기능을 사용할 수 있습니다.  결과 실행 파일에서   `_flushall` 을 호출해 모든 버퍼의 내용을 디스크에 씁니다.  `_flushall` 및 `fflush`은 Commode.obj에만 영향받습니다.  
  
 디스크에 커밋 기능 제어에 대한 자세한 내용은  [I\/O 스트림](../../c-runtime-library/stream-i-o.md),  [위해 fopen](../../c-runtime-library/reference/fopen-wfopen.md), 및  [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)을 참조하십시오.  
  
 이 함수는 스레드 호출을 잠그기 때문에 스레드는 안전합니다.  비잠금 버전을 위해 `_fflush_nolock`을 참조하세요.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fflush`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
  **`테스트 테스트` `테스트 테스트`네 개의 단어로 된 문장을 scanf로 입력합니다. 테스트**  
**이**   
**이 선언은 아래 선언과 같습니다.**  
**a**  
**테스트**  
**gets로 같은 문장을 입력합니다. 테스트**  
**테스트**   
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)