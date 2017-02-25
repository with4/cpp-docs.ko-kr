---
title: "_ftell_nolock, _ftelli64_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64_nolock"
  - "_ftell_nolock"
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
  - "_ftelli64_nolock"
  - "ftelli64_nolock"
  - "ftell_nolock"
  - "_ftell_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftell_nolock 함수"
  - "_ftelli64_nolock 함수"
  - "파일 포인터[C++], 현재 위치 가져오기"
  - "ftell_nolock 함수"
  - "ftelli64_nolock 함수"
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _ftell_nolock, _ftelli64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드를 잠그지 않고 파일 포인터의 현재 위치를 가져옵니다.  
  
## 구문  
  
```  
long _ftell_nolock(   
   FILE *stream   
);  
__int64 _ftelli64_nolock(   
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체를 지정합니다.  
  
## 반환 값  
 `ftell` 및 `_ftelli64`와 동일합니다.  자세한 내용은 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)을 참조하십시오.  
  
## 설명  
 이러한 함수는 각각 `ftell` 및 `_ftelli64`의 잠겨 있지 않은 버전입니다.  함수들은 다른 스레드의 간섭으로부터 보호받지 못하는 것을 제외하고는 `ftell` 및 `_ftelli64`와 동일합니다.  이러한 함수는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다.  단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`ftell_nolock`|\<stdio.h\>|\<\<errno.h\>\>|  
|`_ftelli64_nolock`|\<stdio.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)