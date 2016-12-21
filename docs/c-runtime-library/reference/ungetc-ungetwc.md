---
title: "ungetc, ungetwc | Microsoft Docs"
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
  - "ungetwc"
  - "ungetc"
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
  - "_ungettc"
  - "ungetwc"
  - "ungetc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ungettc 함수"
  - "문자, 스트림으로 다시 푸시"
  - "ungetc 함수"
  - "ungettc 함수"
  - "ungetwc 함수"
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ungetc, ungetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 문자를 다시 푸시합니다.  
  
## 구문  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 문자입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 성공적으로, 각이 함수는 문자 인수 `c`*.* 를 반환합니다. 이 `c` 은 다시 푸시되어 넣어지는 경우나 읽어진 문자가 아닌 경우, 입력 스트림은 변화하지 않고 `ungetc` 은 `EOF`을 반환합니다; `ungetwc` 은 `WEOF`반환합니다.  `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, `EOF` 혹은 `WEOF` 은 반환되고 `errno` 은 `EINVAL`을 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이 `ungetc` 함수는 `stream` 으로 돌아온 `c` 문자를 푸시하고 파일 끝 표시기를 지웁니다.  스트림을 읽을 수 있도록 열려있어야 합니다.  이 `stream` 상의 후속 읽기 작업은 `c`*.* 을 시작합니다. 이 `ungetc` 를 무시하고 사용하여 스트림의 `EOF` 를 밀어넣으려는 시도입니다.  
  
 문자는 `fflush`, `fseek`, `fsetpos`, 또는 `rewind` 가 문자가 스트림으로 부터 읽어지기 전에 호출되는 경우 `ungetc` 가 지워져서 스트림을 대체합니다.  파일 위치 표시기 문자가 push back 전의 값을 갖게 됩니다.  스트림에 해당 외부 저장 장치는 변경되지 않습니다.  성공적인 `ungetc` 은 푸시 백 자를 읽거나 삭제 모든 텍스트 스트림 파일 위치 표시기에 대 한 호출이 지정 되지 않습니다.  각 성공적인 `ungetc` 는 이진 스트림이 파일 위치 표시기에 대한 콜이 감소 합니다. 경우 해당 값이 호출 전에 0으로 값이 정의된 호출 후 입니다.  
  
 이 `ungetc` 이 읽기 또는 두 호출 사이의 작업 파일 위치를 지정 하지 않고 두 번 호출 되는 경우, 결과는 예측할 수 없습니다.  이 `fscanf` 가 호출된 후에, `ungetc` 를 호출하는 것은 수행 되어온 \( `getc`와 같은\) 또 다른 읽기 작업을 실행하지 않으면 실패할 것입니다.  이는 `fscanf` 이 그 자체로 `ungetc` 을 호출하였기 때문입니다.  
  
 `ungetwc` 는 `ungetc` 의 와이드 문자 버전입니다.  그러나, 각 성공적인 `ungetwc` 는 호출 텍스트 또는 이진 스트림의 파일 위치 표시기의 값에 대해 지정되지 않은 모든 푸시 백 자를 읽거나 삭제 될 때까지 입니다.  
  
 이러한 함수는 스레드로부터 안전하고 실행하는 동안 중요한 데이터를 잠급니다.  비잠금 버전을 위해 [\_ungetc\_nolock, \_ungetwc\_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ungetc`|\<stdio.h\>|  
|`ungetwc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
  **`521a`Number \= 521**  
**스트림에서 다음 문자 \= 'a'**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)