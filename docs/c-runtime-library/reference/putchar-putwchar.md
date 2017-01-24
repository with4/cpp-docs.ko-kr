---
title: "putchar, putwchar | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putchar"
  - "putwchar"
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
  - "putchar"
  - "putwchar"
  - "_puttchar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_puttchar 함수"
  - "문자, 작성"
  - "putchar 함수"
  - "putwchar 함수"
  - "표준 출력, 쓰기"
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# putchar, putwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**stdout** 에 문자를 작성합니다.  
  
## 구문  
  
```  
  
      int putchar(  
   int c   
);  
wint_t putwchar(  
   wchar_t c   
);  
```  
  
#### 매개 변수  
 `c`  
 쓸 문자입니다.  
  
## 반환 값  
 작성된 문자를 반환합니다.  오류 또는 파일 끝 조건을 나타내기 위해 `putc` 와 `putchar` 가 `EOF` 를 반환합니다; `putwc` 와 `putwchar` 가 **WEOF** 를 반환합니다.  4개의 모든 루틴에대해, 오류 또는 파일의 끝을 확인하기 위해 [ferror](../../c-runtime-library/reference/ferror.md) 또는 [feof](../../c-runtime-library/reference/feof.md) 를 사용하십시오.   `stream` 의 null 포인터를 전달하는 경우, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 예외를 생성합니다.  계속해서 실행하도록 허용된 경우, `EOF` 또는 **WEOF** 를 반환하고 `errno` 를 `EINVAL` 로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이 `putc` 루틴은 현재 위치의 출력 `stream` 에 단일 문자 `c` 를 작성합니다.  이 `putc` 에 전달될 수 있는 정수는 8비트 이하로 작성된 정수입니다.  이 `putchar` 루틴은 **putc\(** `c`**, stdout \)** 와 같습니다.  각 루틴에 대해, 읽기 오류가 발생 하는 경우 스트림에 대한 오류 표시가 설정됩니다.  `putc` 와 `putchar` 는 각각 `fputc` 와 `_fputchar` 와 유사합니다. 하지만 둘다 함수와 매크로로 구현됩니다.\( [Choosing Between Functions and Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)를 참조하십시오.\)  `putwc` 와 `putwchar` 는 각각 `putc` 와 `putchar` 의 와이드 문자 버전입니다.  
  
 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 것을 제외하고 동일합니다.  이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다.  단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_puttchar`|`putchar`|`putchar`|**putwchar**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`putchar`|\<stdio.h\>|  
|`putwchar`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_putchar.c  
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
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putchar( *p );  
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