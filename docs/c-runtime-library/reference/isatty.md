---
title: "isatty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isatty"
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
  - "isatty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "isatty 함수"
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _isatty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 설명자 연결된 문자 장치인지 확인합니다.  
  
## 구문  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 테스트할 장치를 참조하는 파일 설명자입니다.  
  
## 반환 값  
 `_isatty` 은 문자 장치와 관련된 설명자가 0이 아닌 값을 반환합니다.  그렇지 않으면, `_isatty` 에서는 0을 반환합니다.  
  
## 설명  
 이 `_isatty` 는 함수 여부를 문자 장치 \(터미널, 콘솔, 프린터 또는 직렬 포트\)에 연결된 `fd` 을 결정합니다.  
  
 이 함수는 해당 `fd` 매개 변수의 유효성을 검사합니다.  여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `fd` 이 나쁜 파일 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 0을 반환하고 `errno` 를 `EBADF`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_isatty`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## 샘플 출력  
  
```  
stdout has not been redirected to a file  
```  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)