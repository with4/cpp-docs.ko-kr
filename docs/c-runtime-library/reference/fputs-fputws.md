---
title: "fputs, fputws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fputs"
  - "fputws"
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
  - "fputs"
  - "fputws"
  - "_fputts"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputts 함수"
  - "fputs 함수"
  - "fputts 함수"
  - "fputws 함수"
  - "스트림, 문자열 쓰기"
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# fputs, fputws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 문자열을 씁니다.  
  
## 구문  
  
```  
int fputs(   
   const char *str,  
   FILE *stream   
);  
int fputws(   
   const wchar_t *str,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `str`  
 출력 문자열  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 각이 함수를 성공한 경우 음수가 아닌 값을 반환합니다.  에러에서, `fputs` 과 `fputws` 는 `EOF`을 반환합니다.  이 `str` 또는 `stream` 가 NULL 포인터인 경우, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `fputs` 은 `EOF`을 반환하고, `fputws` 은 `WEOF`을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 각 이러한 함수는 현재 위치의 `stream` 을 출력하는 `str` 을 복사합니다.  `fputws` 는 와이드 문자 인수 `str` 를 `stream` 이 텍스트로 열리는지 아닌지에 따른 멀티 문자 문자열 혹은 와이드 문자 문자열 `stream` 으로 복사합니다.  두 함수는 null 종결 문자를 복사합니다.  
  
 스트림이 ANSI 모드에서 열린 경우 두 함수는 동일하게 동작합니다.  `fputs`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_fputts`|`fputs`|`fputs`|`fputws`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fputs`|\<stdio.h\>|  
|`fputws`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fputs.c  
// This program uses fputs to write  
// a single line to the stdout stream.  
  
#include <stdio.h>  
  
int main( void )  
{  
   fputs( "Hello world from fputs.\n", stdout );  
}  
```  
  
  **Hello world from fputs.**   
## 해당 .NET Framework 항목  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)