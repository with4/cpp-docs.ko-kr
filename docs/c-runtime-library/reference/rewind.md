---
title: "rewind | Microsoft Docs"
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
  - "rewind"
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
  - "rewind"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "파일 포인터[C++]"
  - "파일 포인터[C++], 위치 변경"
  - "파일 포인터 위치 변경"
  - "rewind 함수"
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rewind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 포인터가 파일의 시작 부분으로 다시 이동합니다.  
  
## 구문  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 이는 **FILE** 구조체에 대한 포인터입니다.  
  
## 설명  
 **rewind** 함수는 파일의 시작 부분의 `stream` 에 관한 파일 포인터의 위치를 재 설정합니다.  **rewind** 를 호출 하는 것과 유사합니다.  
  
 **\(void\) fseek\(** `stream`**, 0L,** `SEEK_SET` **\);**  
  
 그러나, `fseek` 와 달리 **rewind** 는 파일 끝 표시기 뿐만 아니라 스트림에 대해 오류 표시를 지웁니다.  또한, `fseek` 와 달리 **rewind** 는 포인터가 성공적으로 이동 했는지에 대한 여부를 나타내는 값을 반환하지 않습니다.  
  
 키보드 버퍼를 지우기 위해, 기본적으로 키보드와 관련된 `stdin` 을 사용하여 **rewind** 를 사용하십시오.  
  
 스트림이 `NULL` 포인터인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다.   계속해서 실행하도록 허용된 경우, 이 함수는 반환하고 `errno` 는 `EINVAL` 로 설정됩니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**rewind**|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## Output  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)