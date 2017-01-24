---
title: "_chsize_s | Microsoft Docs"
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
  - "_chsize_s"
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
  - "chsize_s"
  - "_chsize_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chsize_s 함수"
  - "chsize_s 함수"
  - "파일[C++], 크기 변경"
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chsize_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 크기를 수정합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 이 버전은 보안 향상 기능이 포함된 [\_chsize](../../c-runtime-library/reference/chsize.md) 의 버전입니다.  
  
## 구문  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 설명자입니다.  
  
 `size`  
 새 파일의 길이\(바이트\)입니다.  
  
## 반환 값  
 만일 파일의 크기가 성공적으로 변경되면, `_chsize_s`  은 0을 반환합니다.  오류는 0이 아닌 반환값을 나타냅니다: 만일 지정된 파일이 접근에 대하여 허가되지 않은 경우, 반환값은 `EACCES` 이고, 만일 지정된 파일이 읽기 전용이거나 설명자가 잘못된 경우, `EBADF` , 만일 장치에 공간이 없는 경우, `ENOSPC` 로, 크기가 0보다 적은 경우, `EINVAL` 을 반환합니다.  `errno`  같은 값으로 설정합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_chsize_s`  함수는 `size` 로 지정된 길이로 `fd` 를 사용하여 파일을 자르거나 확장합니다.  파일은 쓰기를 허용 하는 모드에서 열려 있어야 합니다.  파일이 확장되는 경우, null 문자\('\\0'\)이 추가됩니다.  파일이 잘린경우, 파일의 본래 길이로 단축된 파일의 끝으로부터 모든 데이터가 손실됩니다.  
  
 \_chsize\_s 은 파일 크기로 64 비트 정수를 사용하고, 따라서 4GB 보다 큰 파일 크기를 처리할 수 있습니다.  `_chsize` 은 32 비트 파일로 크기가 제한됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만일 `fd` 이 유효한 파일 설명자가 아니거나 0보다 적은 크기를 가지는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기를 호출합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_chsize_s`|\<io.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)