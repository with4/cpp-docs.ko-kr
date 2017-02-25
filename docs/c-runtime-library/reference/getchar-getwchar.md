---
title: "getchar, getwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getchar"
  - "getwchar"
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
  - "getwchar"
  - "GetChar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gettchar 함수"
  - "문자, 읽기"
  - "gettchar 함수"
  - "getwchar 함수"
  - "표준 입력, 읽기"
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# getchar, getwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 입력에서 문자를 읽습니다.  
  
## 구문  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## 반환 값  
 읽은 문자를 반환합니다.  읽기 오류 또는 파일 끝 조건을 나타내기 위해 `getchar` `returns EOF`, 및 `getwchar` 는 `WEOF`을 반환합니다.  `getchar`에 대해 `ferror` 또는 `feof` 을 사용하여 오류 또는 파일의 끝을 확인하세요.  
  
## 설명  
 각 루틴은 `stdin` 의 단일 문자를 읽고 다음 문자를 가리키도록 연결된 파일 포인터를 증가 시킵니다.  `getchar` 는 [\_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)과 같지만 매크로 및 함수로 구현 됩니다.  
  
 이러한 함수는 호출 스레드를 잠그고, 그러므로 안전 스레드가 됩니다.  비잠금 버전을 위해 [\_getchar\_nolock, \_getwchar\_nolock](../../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`getchar`|\<stdio.h\>|  
|`getwchar`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`이 텍스트`입력은: 이 텍스트**   
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)