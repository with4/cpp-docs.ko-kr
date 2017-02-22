---
title: "putc, putwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putwc"
  - "putc"
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
  - "_puttc"
  - "putwc"
  - "putc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_puttc 함수"
  - "문자, 작성"
  - "putc 함수"
  - "puttc 함수"
  - "putwc 함수"
  - "스트림, 문자 쓰기"
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# putc, putwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 문자를 씁니다.  
  
## 구문  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `c`  
 쓸 문자입니다.  
  
 `stream`  
 이는 **FILE** 구조체에 대한 포인터입니다.  
  
## 반환 값  
 작성된 문자를 반환합니다.  오류 또는 파일 끝 조건을 나타내기 위해 `putc` 와 `putchar` 가 `EOF` 를 반환합니다; `putwc` 와 `putwchar` 가 **WEOF** 를 반환합니다.  4개의 모든 루틴에대해, 오류 또는 파일의 끝을 확인하기 위해 [ferror](../../c-runtime-library/reference/ferror.md) 또는 [feof](../../c-runtime-library/reference/feof.md) 를 사용하십시오.  여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `stream` 이 null 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF` 혹은 **WEOF** 를 반환하고 `EINVAL`를 `errno` 로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이 `putc` 루틴은 현재 위치의 출력 `stream` 에 단일 문자 `c` 를 작성합니다.  이 `putc` 에 전달될 수 있는 정수는 8비트 이하로 작성된 정수입니다.  이 `putchar` 루틴은 **putc\(** `c`**, stdout \)** 와 같습니다.  각 루틴에 대해, 읽기 오류가 발생 하는 경우 스트림에 대한 오류 표시가 설정됩니다.  `putc` 와 `putchar` 는 각각 `fputc` 와 `_fputchar` 와 유사합니다. 하지만 둘다 함수와 매크로로 구현됩니다.\( [Choosing Between Functions and Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)를 참조하십시오.\)  `putwc` 와 `putwchar` 는 각각 `putc` 와 `putchar` 의 와이드 문자 버전입니다.  `putwc` 및 `putc`는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `putc` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 것을 제외하고 동일합니다.  자세한 내용은 **\_putc\_nolock, \_putwc\_nolock**를 보세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`putc`|\<stdio.h\>|  
|`putwc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## Output  
  
```  
This is the line of output  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)