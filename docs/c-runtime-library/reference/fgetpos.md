---
title: "fgetpos | Microsoft Docs"
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
  - "fgetpos"
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
  - "fgetpos"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fgetpos 함수"
  - "스트림, 파일 위치 표시기"
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림의 파일 위치 지시자를 가져옵니다.  
  
## 구문  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### 매개 변수  
 `stream`  
 대상 스트림입니다.  
  
 `pos`  
 저장소 위치 표시기입니다.  
  
## 반환 값  
 만일 성공하면, `fgetpos` 은 0을 반환합니다.  실패 시, 0이아닌 값을 반환하고 `errno` 을 \(STDIO.H에서 정의된\)다음 매니패스트 상수의 하나로 설정합니다: 이것은 지정된 스트림이 유효하지 않은 파일 포인터나 접근이 불가능한 `EBADF` 이거나 null포인터처럼, `pos` 의 값 또는 `stream` 을 의미하는 `EINVAL` 입니다.  만일 `stream` 또는 `pos` 는 `NULL` 포인터인 경우, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서 설명된 대로 잘못된 매개변수 처리기를 호출합니다.  
  
## 설명  
 `fgetpos` 함수는 `pos` 로 지정된 객체에 이것을 저장하고 `stream` 파일 위치 지시자의 현재 값을 가져오는 함수입니다.  `fsetpos` 함수는 `fgetpos` 이 호출된 시간에 이것의 위치에 대한 `stream` 인수의 포인터를 재설정하기위해 `pos` 에 저장된 정보를 사용할 수 있습니다.  `pos` 값은 내부 형식에 저장되고 `fgetpos` 와 `fsetpos` 에 의해서만 사용에 대해 만들어집니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fgetpos`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## 입력: crt\_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### 출력 crt\_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)