---
title: "_fgetchar, _fgetwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fgetchar"
  - "_fgetwchar"
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
  - "fgetwchar"
  - "_fgettchar"
  - "_fgetchar"
  - "_fgetwchar"
  - "fgettchar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetchar 함수"
  - "_fgettchar 함수"
  - "_fgetwchar 함수"
  - "fgetchar 함수"
  - "fgettchar 함수"
  - "fgetwchar 함수"
  - "표준 입력, 읽기"
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fgetchar, _fgetwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 `stdin` 에서 문자를 읽습니다.  
  
## 구문  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## 반환 값  
 `_fgetchar` 은 `int` 으로 읽어진 문자를 반환하거나 파일의 끝 혹은 오류를 나타내는 `EOF` 을 반환합니다.  **\_**`fgetwchar` 읽을 문자나 파일의 끝 혹은 오류를 나타내는 `WEOF` 를 반환에 해당하는 와이드 문자를 , [wint\_t](../../c-runtime-library/standard-types.md)로써, 반환합니다.  두 함수를 위해, 오류는 파일과 끝 조건을 구분하기 위해 `feof` 또는 `ferror` 사용하세요.  
  
## 설명  
 이러한 함수는 `stdin`에서 단일 문자를 읽습니다.  함수 다음 증가 관련된 파일 포인터\(정의\)하는 경우 다음 문자를 가리킵니다.  스트림이 파일의 끝에 스트림의 파일 끝 지표 설정됩니다.  
  
 `_fgetchar`는 `fgetc( stdin )`와 같습니다.  이는 `getchar` 와 동일하지만 함수와 매크로 보다는 오직 함수로서만 구현됩니다.  `_fgetwchar` 는 `_fgetchar` 의 와이드 문자 버전입니다.  
  
 이러한 함수는 ANSI 표준 호환되지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fgetchar`|\<stdio.h\>|  
|`_fgetwchar`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fgetchar.c  
// This program uses _fgetchar to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[81];  
   int  i, ch;  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = _fgetchar();  
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetchar();  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
}  
```  
  
  **`첫째 줄. 두 줄입니다.`선 하나.**  
**두 줄입니다.**   
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)