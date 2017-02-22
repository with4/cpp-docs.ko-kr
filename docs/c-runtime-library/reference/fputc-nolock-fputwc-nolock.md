---
title: "_fputc_nolock, _fputwc_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fputwc_nolock"
  - "_fputc_nolock"
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
  - "_fputc_nolock"
  - "fputwc_nolock"
  - "fputc_nolock"
  - "fputtc_nolock"
  - "_fputwc_nolock"
  - "_fputtc_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputc_nolock 함수"
  - "_fputtc_nolock 함수"
  - "_fputwc_nolock 함수"
  - "fputc_nolock 함수"
  - "fputtc_nolock 함수"
  - "fputwc_nolock 함수"
  - "스트림, 문자 쓰기"
ms.assetid: c63eb3ad-58fa-46d0-9249-9c25f815eab9
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _fputc_nolock, _fputwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드를 잠그지 않고 스트림에 문자를 씁니다.  
  
## 구문  
  
```  
int _fputc_nolock(  
   int c,  
   FILE *stream   
);  
wint_t _fputwc_nolock(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `c`  
 쓸 문자입니다.  
  
 `stream`  
 이 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 이러한 함수의 각각은 작성 된 문자를 반환합니다.  이 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)에 대한 자세한 내용은 을 참조하십시오.  
  
## 설명  
 `_fputc_nolock` 과 `_fputwc_nolock` 는 각 다른 스레드의 간섭으로 부터 보호되지 않은 `fputc` 과 `fputwc` 을 제외하는 것이 동일합니다.  이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다.  단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
 스트림이 ANSI 모드에서 열린 경우 두 함수는 동일하게 동작합니다.  `_fputc_nolock`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fputtc_nolock`|`_fputc_nolock`|`_fputc_nolock`|`_fputwc_nolock`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fputc_nolock`|\<stdio.h\>|  
|`_fputwc_nolock`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fputc_nolock.c  
// This program uses _fputc_nolock  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of _fputc_nolock!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && _fputc_nolock( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **This is a test of \_fputc\_nolock\!\!**   
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)