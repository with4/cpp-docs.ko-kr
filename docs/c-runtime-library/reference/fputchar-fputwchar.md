---
title: "_fputchar, _fputwchar | Microsoft Docs"
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
  - "_fputchar"
  - "_fputwchar"
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
  - "fputtchar"
  - "_fputwchar"
  - "fputwchar"
  - "_fputtchar"
  - "fputchar"
  - "_fputchar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fputchar 함수"
  - "_fputtchar 함수"
  - "_fputwchar 함수"
  - "fputchar 함수"
  - "fputtchar 함수"
  - "fputwchar 함수"
  - "표준 출력, 쓰기"
ms.assetid: b92ff600-a924-4f2b-b0e7-3097ee31bdff
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fputchar, _fputwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 `stdout`에 문자를 씁니다.  
  
## 구문  
  
```  
int _fputchar(  
   int c   
);  
wint_t _fputwchar(  
   wchar_t c   
);  
```  
  
#### 매개 변수  
 `c`  
 쓸 문자입니다.  
  
## 반환 값  
 이러한 함수의 각각은 작성 된 문자를 반환합니다.  이 `_fputchar` 에 대해 `EOF` 의 반환값은 오류를 나타냅니다.  이 `_fputwchar` 에 대해 `WEOF` 의 반환값은 오류를 나타냅니다.  c 가 `NULL`인 경우, 이러한함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명된 잘못된 매개 변수 예외를 생성합니다.  계속해서 실행하도록 허용된 경우, `EOF`\(혹은`WEOF`\) 과 `errno` 을 `EINVAL`으로 설정합니다.  
  
 이러한 반환 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이러한 함수 모두 단일 문자 `c` 을 `stdout` 으로 쓰고 적절한 지표를 충당합니다.  `_fputchar` 는 `fputc(``stdout )`와 같습니다.  이는 `putchar` 와 동일하지만 함수와 매크로 보다는 오직 함수로서만 구현됩니다.  이 `fputc` 및 `putchar`와 달리, 이러한 함수는 ANSI 표준 호환되지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fputtchar`|`_fputchar`|`_fputchar`|`_fputwchar`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fputchar`|\<stdio.h\>|  
|`_fputwchar`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fputchar.c  
// This program uses _fputchar  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
    char strptr[] = "This is a test of _fputchar!!\n";  
    char *p = NULL;  
  
    // Print line to stream using _fputchar.   
    p = strptr;  
    while( (*p != '\0') && _fputchar( *(p++) ) != EOF )  
      ;  
}  
```  
  
  **This is a test of \_fputchar\!\!**   
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)