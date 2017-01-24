---
title: "_getw | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getw"
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
  - "_getw"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getw 함수"
  - "getw 함수"
  - "정수, 스트림에서 가져오기"
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 정수를 가져옵니다.  
  
## 구문  
  
```  
int _getw(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 이 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `_getw` 는 읽기 정수 값을 반환 합니다.  반환 값인 `EOF` 는 오류 또는 파일의 끝을 나타냅니다.  그러나 `EOF` 값은 또한 정당한 정수 값이기 때문에, `feof` 또는 `ferror` 는 EOF 또는 오류 조건을 확인하는데 사용됩니다.  `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EOF` 을 반환합니다.  
  
## 설명  
 이 `_getw` 함수는 다음 이진수 값 형식인 `int` 를 `stream` 과 연관된 파일로부터 읽어오며, 연관된 파일 포인터를 \(하나 있는 경우\) 다음 읽지 않은 문자를 가르키는 포인터로 증가시킵니다.  `_getw` 는 스트림에서 항목의 모든 특별한 맞춤을 가정하지 않습니다.  포팅 관련 문제는 `_getw` 를 발생시킵니다. 왜냐하면 `int` 형식의 크기와 `int` 형식인 바이트의 순서는 시스템간에 다르기 때문입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getw`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_getw.c  
// This program uses _getw to read a word  
// from a stream, then performs an error check.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   int i;  
  
   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )  
      printf( "Couldn't open file\n" );  
   else  
   {  
      // Read a word from the stream:  
      i = _getw( stream );  
  
      // If there is an error...  
      if( ferror( stream ) )  
      {  
         printf( "_getw failed\n" );  
         clearerr_s( stream );  
      }  
      else  
         printf( "First data word in file: 0x%.4x\n", i );  
      fclose( stream );  
   }  
}  
```  
  
## 입력: crt\_getw.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
First data word in file: 0x656e694c  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_putw](../../c-runtime-library/reference/putw.md)