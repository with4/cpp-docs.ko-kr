---
title: "_flushall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_flushall"
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
  - "_flushall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flushall 함수"
  - "스트림 플러시"
  - "스트림, 플러시"
  - "_flushall 함수"
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _flushall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 스트림을 플러시; 모든 버퍼를 지웁니다.  
  
## 구문  
  
```  
int _flushall( void );  
```  
  
## 반환 값  
 `_flushall`은 열려 있는 스트림 \(입 \/ 출력\)의 수를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 기본적으로,  `_flushall`  함수는 열기 출력 스트림과 사용하여 연결된 모든 버퍼의 내용을 해당 파일에 씁니다.  오픈된 입력 스트림 연관되는 모든 버퍼는 현재 내용이 삭제됩니다. \(이 버퍼는 보통 자동으로 디스크에 데이터를 쓸 수 있는 최적의 시간을 결정하는 운영체제에서 정상적으로 유지됩니다: 버퍼가 꽉 찼을 때, 스트림을 닫을 때 또는 프로그램이 정상적으로 스트림을 닫지 않고 종료될 때입니다.\)  
  
 읽기가  `_flushall` 의 호출을 가져오는 경우, 버퍼의 입력 파일에서 새로운 데이터를 읽습니다.   `_flushall` 를 호출한 후 모든 스트림이 열립니다.  
  
 런타임 라이브러리의 디스크에 커밋 기능을 통해 중요한 데이터가 운영체제 버퍼 대신 디스크에 직접 작성되었는지 확인할 수 있습니다.  기존 프로그램을 다시 작성 하지 않고도 Commode.obj에 프로그램의 개체 파일을 연결하여 이 기능을 사용할 수 있습니다.  결과 실행 파일에서   `_flushall` 을 호출해 모든 버퍼의 내용을 디스크에 씁니다.  오직  `_flushall`  및  `fflush` 은 Commode.obj의 영향만을 받습니다.  
  
 디스크에 커밋 기능 제어에 대한 자세한 내용은  [I\/O 스트림](../../c-runtime-library/stream-i-o.md),  [위해 fopen](../../c-runtime-library/reference/fopen-wfopen.md), 및  [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)을 참조하십시오.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_flushall`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
  **플러시된 3 스트림이 있습니다.**   
## 해당 .NET Framework 항목  
  
-   [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
-   [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)  
  
-   [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)  
  
-   [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)