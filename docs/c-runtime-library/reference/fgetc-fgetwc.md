---
title: "fgetc, fgetwc | Microsoft Docs"
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
  - "fgetwc"
  - "fgetc"
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
  - "_fgettc"
  - "fgetwc"
  - "fgetc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgettc 함수"
  - "문자, 읽기"
  - "fgetc 함수"
  - "fgettc 함수"
  - "fgetwc 함수"
  - "스트림에서 문자 읽기"
  - "스트림, 문자 읽기"
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgetc, fgetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 문자를 읽습니다.  
  
## 구문  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `fgetc` 은 `int` 으로 읽어진 문자를 반환하거나 파일의 끝 혹은 오류를 나타내는 `EOF` 을 반환합니다.  `fgetwc` 는 [wint\_t](../../c-runtime-library/standard-types.md) 로서 읽을 문자나 파일의 끝 또는 오류를 나타내기 위한 `WEOF` 을 반환에 해당하는 와이드 문자를 반환합니다.  두 함수를 위해, 오류는 파일과 끝 조건을 구분하기 위해 `feof` 또는 `ferror` 사용하세요.  읽기 오류가 발생 하는 경우 스트림에 대한 오류 표시가 설정 됩니다.  `stream` 가 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 `fgetc` 및 `fgetwc` 은 잘못된 매개 변수 처기리를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EOF`을 반환합니다.  
  
## 설명  
 각 함수들은 `stream` 와 관련된 파일의 현재 위치에서 단일 문자를 읽습니다.  함수 다음 증가 관련된 파일 포인터\(정의\)하는 경우 다음 문자를 가리킵니다.  스트림이 파일의 끝에 스트림의 파일 끝 지표 설정됩니다.  
  
 `fgetc` 는 `getc` 와 동일하지만 함수와 매크로 보다는 함수로서만 구현 됩니다.  
  
 `fgetwc` 은 `fgetc` 의 와이드 문자 버전입니다. 이것은 `c` 를 `stream` 가 텍스트 모드 또는 이진 모드에서 열려 있는지 여부에 따라 멀티 바이트 또는 와이드 문자로 읽습니다.  
  
 이 `_nolock` 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 것을 제외하고 동일합니다.  
  
 와이드 문자 및 멀티 바이트 문자 텍스트 및 이진 모드에서 처리 하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드에서 유니코드 스트림 I\/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md) 을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fgetc`|\<stdio.h\>|  
|`fgetwc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fgetc.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:  
   fopen_s( &stream, "crt_fgetc.txt", "r" );  
   if( stream == NULL )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":   
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = fgetc( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Input: crt\_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Line one.  
Line two.  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)