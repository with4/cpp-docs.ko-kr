---
title: "fputc, fputwc | Microsoft Docs"
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
  - "fputc"
  - "fputwc"
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
  - "fputc"
  - "fputwc"
  - "_fputtc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fputtc 함수"
  - "fputc 함수"
  - "fputtc 함수"
  - "fputwc 함수"
  - "스트림, 문자 쓰기"
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fputc, fputwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 문자를 씁니다.  
  
## 구문  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `c`  
 쓸 문자입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 이러한 함수의 각각은 작성 된 문자를 반환합니다.   `fputc` 에 대해 `EOF` 의 반환값은 오류를 나타냅니다.   `fputwc` 에 대해 `WEOF` 의 반환값은 오류를 나타냅니다.   `stream` 이 `NULL` 인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이러한 함수의 각각은 단일 문자 `c` 를 관련된 파일 위치 표시기\(정의된 경우\)에 의해 나타내진 파일의 위치에 작성하고 적절하게 표시기를 이동합니다.   `fputc` 및 `fputwc` 의 경우, 해당 파일은 `stream`*.* 과 관련됩니다. 파일이 위치지정 요청을 지원하지 않거나 추가 모드에서 열린경우, 문자는 스트림의 끝에 추가됩니다.  
  
 스트림이 ANSI 모드에서 열린 경우 두 함수는 동일하게 동작합니다.  `fputc`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 이 `_nolock` 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 것을 제외하고 동일합니다.  자세한 내용은[\_fputc\_nolock, \_fputwc\_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md) 을 참조하십시오.  
  
 루틴 별 설명은 다음과 같습니다.  
  
|루틴|설명|  
|--------|--------|  
|`fputc`|`putc` 와 동일하지만 함수와 매크로 보다는 오직 함수로서만 구현됩니다.|  
|`fputwc`|`fputc` 의 와이드 문자 버전입니다.   `stream` 이 텍스트 모드나 이진 모드로 열리는지에 대한 여부에 따라 `c` 를 멀티 바이트 문자나 와이드 문자로 작성합니다.|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fputc`|\<stdio.h\>|  
|`fputwc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **This is a test of fputc\!\!**   
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)