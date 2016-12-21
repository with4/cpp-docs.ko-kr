---
title: "fclose, _fcloseall | Microsoft Docs"
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
  - "fclose"
  - "_fcloseall"
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
  - "fclose"
  - "_fcloseall"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fclose 함수"
  - "스트림, 닫기"
  - "_fcloseall 함수"
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fclose, _fcloseall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나의 스트림을 닫거나\(`fclose`\) 모든 열린 스트림을 닫습니다.\(`_fcloseall`\)  
  
## 구문  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 만일 스트림이 성공적으로 닫힌 경우, `fclose` 은 0을 반환합니다.  `_fcloseall` 은 총 닫힌 스트림의 수를 반환합니다.  오류를 나타내기 위해 두 함수는 모두 `EOF` 를 반환합니다.  
  
## 설명  
 `fclose` 함수는 `stream` 을 종료합니다.  `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, `fclose` 는 `errno` 를 `EINVAL` 로 설정하고 `EOF`를 반환합니다.  `stream` 포인터가 항상 이 함수를 호출하기 전에 체크되는지 확인하는 것이 좋습니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 `_fcloseall` 함수는 `stdin`, `stdout`, `stderr` \(그리고, MS\-DOS에서 `_stdaux` 와 `_stdprn`\)를 제외한 모든 열린 스트림을 닫습니다.  이것은 `tmpfile`에 의해 생성된 모든 임시파일들 또한 닫고 삭제합니다.  두 함수에서, 스트림에 관련된 모든 버퍼들이 닫기 전에 플러쉬됩니다.  시스템에서 할당된 버퍼는 스트림의 닫을 때 해제됩니다.  `setbuf` 와 `setvbuf` 를 사용하여 사용자 지정된 버퍼들은 자동적으로 해제되지 않습니다.  
  
 **참고:**  스트림을 닫기위해 이러한 함수를 사용할 때, 스트림 뿐만 아니라, OS 파일 핸들\(또는 소켓\)과 기본 파일 설명자가 닫힙니다.  따라서, 파일이 파일 핸들이나 파일 설명자로써 처음 열리거나 `fclose` 을 사용하여 닫힌 경우, 파일 설명자을 닫기 위해 `_close` 역시 호출되지 않습니다; 파일 핸들을 닫기위해 Win32 함수 `CloseHandle` 는 호출되지 않습니다.  
  
 `fclose` 와 `_fcloseall` 는 다른 스레드에 대한 간섭으로부터 보호하기 위한 코드를 포함합니다.  `fclose` 의 비잠금 버전에 대해, `_fclose_nolock`를 참고하세요.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fclose`|\<stdio.h\>|  
|`_fcloseall`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)  
  
-   [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)  
  
-   [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)  
  
-   [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)  
  
-   [System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)  
  
-   [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)  
  
-   [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)  
  
-   [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)  
  
-   [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)