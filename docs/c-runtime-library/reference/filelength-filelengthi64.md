---
title: "_filelength, _filelengthi64 | Microsoft Docs"
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
  - "_filelengthi64"
  - "_filelength"
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
  - "_filelength"
  - "_filelengthi64"
  - "filelengthi64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_filelength 함수"
  - "_filelengthi64 함수"
  - "filelength 함수"
  - "filelengthi64 함수"
  - "파일[C++], 길이"
  - "길이, 파일"
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _filelength, _filelengthi64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일의 길이를 가져옵니다.  
  
## 구문  
  
```  
long _filelength(   
   int fd   
);  
__int64 _filelengthi64(   
   int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 대상 파일 설명자입니다.  
  
## 반환 값  
 `_filelength` 및 `_filelengthi64` 는 둘다 바이트로 `fd` 와 관련된 대상 파일의 파일 길이를 반환합니다.  여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `fd` 이 잘못된 파일 기술자인 경우 잘못된 매개 변수 처리기가 호출됩니다.  실행을 계속하도록 허용된 경우, 두 함수는 \-1L을 오류를 나타내기 위해 반환하고 `errno` 를 `EBADF` 로 설정합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_filelength`|\<io.h\>|  
|`_filelengthi64`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_chsize](../../c-runtime-library/reference/chsize.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)