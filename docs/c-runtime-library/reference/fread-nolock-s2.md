---
title: "_fread_nolock_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fread_nolock_s"
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
  - "_fread_nolock_s"
  - "stdio/_fread_nolock_s"
dev_langs: 
  - "C"
  - "C++"
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fread_nolock_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 스레드를 잠그지 않고 스트림에서 데이터를 읽습니다.[CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 이 버전의 [fread\_nolock](../../c-runtime-library/reference/fread-nolock.md)에서는 보안 기능이 향상되었습니다.  
  
## 구문  
  
```  
size_t _fread_nolock_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t elementCount,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `buffer`  
 데이터의 저장소 위치입니다.  
  
 `bufferSize`  
 출력 버퍼의 바이트 크기입니다.  
  
 `elementSize`  
 읽을 항목의 크기\(바이트\)입니다.  
  
 `elementCount`  
 읽힐 항목의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 [fread\_s](../../c-runtime-library/reference/fread-s.md)을 참조하세요.  
  
## 설명  
 이 함수는 `fread_s`의 잠기지 않은 버전입니다. 이는 다른 스레드의 방해로부터 보호되지 않는다는 점을 제외하고 `fread_s`와 동일합니다. 이는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 호출 범위에서 이미 스레드 격리를 처리하는 경우에만 이 함수를 사용합니다.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`_fread_nolock_s`|C: \<stdio.h\>; C\+\+: \<cstdio\> 또는 \<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)