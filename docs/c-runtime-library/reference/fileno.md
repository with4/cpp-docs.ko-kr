---
title: "_fileno | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fileno"
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
  - "_fileno"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일 핸들[C++], 스트림에서 가져오기"
  - "fileno 함수"
  - "_fileno 함수"
  - "스트림, 파일 핸들 가져오기"
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _fileno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 연결된 파일 기술자 가져오기  
  
## 구문  
  
```  
int _fileno(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 이 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `_fileno`는 파일 기술자를 반환합니다.  반환되는 오류가 없습니다.  `stream`가 열린 파일을 지정하지 않았을 경우 결과는 정의되지 않습니다.  스트림이 `NULL`인 경우, \_`fileno`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속 실행하는 것이 허용된 경우, 이 함수는 \-1을 반환하고 `errno`을 `EINVAL`로 설정합니다.  
  
 이러한 반환 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
> [!NOTE]
>  `stdout` 또는 `stderr`가 출력 스트림\(예를 들어, 콘솔 윈도우 없는 Windows 응용 프로그램\)과 연결되어 있지 않을 경우, 반환된 파일 기술자는 \-2입니다.  이전 버전에서, 반환된 파일 기술자는 \-1입니다.  이 변경은 응용 프로그램이 오류와 이 상태를 구분하도록 허용합니다.  
  
## 설명  
 `_fileno` 루틴은 `stream`와 현재 연결된 파일 기술자를 반환합니다.  이 루틴은 함수와 매크로 둘 다로서 실행됩니다.  각 구현을 선택하는 것에 대한 추가 정보는, [Choosing Between Functions and Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)를 참조하십시오.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fileno`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fileno.c  
// This program uses _fileno to obtain  
// the file descriptor for some standard C streams.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );  
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );  
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );  
}  
```  
  
  **stdin의 파일 기술자는 0입니다.**  
**stdout의 파일 기술자는 1입니다.**  
**stderr의 파일 기술자는 2입니다.**   
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)