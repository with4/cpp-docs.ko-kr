---
title: "clearerr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clearerr"
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
  - "clearerr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clearerr 함수"
  - "스트림용 오류 표시기"
  - "스트림 오류 표시기 다시 설정"
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# clearerr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 대한 오류 표시를 다시 설정합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 설명  
 `clearerr` 함수는 `stream` 에 대한 파일의 끝 표시기와 오류 표시기를 재설정합니다.  오류 표시기는 자동으로 지워지지 않습니다; 먼저 해당 스트림에 대한 오류 표시기가 재설정되고, 해당 스트림에서 작업들은 호출된 `clearerr`, `fseek` `fsetpos`, `rewind`까지 오류가 반환됩니다.  
  
 `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 을 `EINVAL` 로 설정하고 반환합니다.  `errno` 와 오류코드들에 관한 자세한 정보는 [오류 상수들](../../c-runtime-library/errno-constants.md)을 참고하세요.  
  
 이 함수들의 더 안전한 버전을 사용할 수 있습니다; [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md)를 참고하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`clearerr`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
  **`n` `n`쓰기 오류: 오류 없음**  
**입력하면 오류가 발생합니까? n**  
**읽기오류가 아닙니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)