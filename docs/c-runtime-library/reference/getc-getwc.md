---
title: "getc, getwc | Microsoft Docs"
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
  - "getwc"
  - "getc"
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
  - "_gettc"
  - "getwc"
  - "_gettchar"
  - "getc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettc 함수"
  - "문자, 읽기"
  - "getc 함수"
  - "gettc 함수"
  - "getwc 함수"
  - "getwchar 함수"
  - "스트림에서 문자 읽기"
  - "스트림, 문자 읽기"
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getc, getwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 문자를 읽습니다.  
  
## 구문  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 입력 스트림  
  
## 반환 값  
 읽은 문자를 반환합니다.  읽기 오류 또는 파일 끝 조건을 나타내기 위해 `getc` 는 `EOF` 를 반환하고, `getwc` 는 `WEOF`을 반환합니다.  `getc`에 대해 `ferror` 또는 `feof` 을 사용하여 오류 또는 파일의 끝을 확인하세요.  `stream` 가 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 `getc` 및 `getwc` 은 잘못된 매개 변수 처기리를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF` 를 반환하고 `errno` \(또는 `getwc` 에 대한 `WEOF`\) 를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 각 루틴은 현재 위치에서 파일의 단일 문자를 읽고 다음 문자에 대해 관련된 파일 포인터\(정의 된 경우\) 를 증가시킵니다.  `stream`과 연결된 파일입니다.  
  
 이러한 함수는 호출 스레드를 잠그고, 그러므로 안전 스레드가 됩니다.  비잠금 버전을 위해 [\_getc\_nolock, \_getwc\_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md)을 참조하세요.  
  
 루틴 별 설명은 다음과 같습니다.  
  
|루틴|설명|  
|--------|--------|  
|`getc`|`fgetc` 고 동일하지만 함수와 매크로로 구현 합니다.|  
|`getwc`|`getc` 의 와이드 문자 버전입니다.  `stream` 가 텍스트 모드 또는 이진 모드에 열렸는지에 따라 와이드 문자 또는 멀티 바이트 문자를 읽습니다.|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`getc`|\<stdio.h\>|  
|`getwc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## Input: crt\_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Input was: Line one.  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)