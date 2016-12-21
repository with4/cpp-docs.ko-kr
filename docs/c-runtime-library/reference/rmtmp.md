---
title: "_rmtmp | Microsoft Docs"
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
  - "_rmtmp"
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
  - "rmtmp"
  - "_rmtmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rmtmp 함수"
  - "파일[C++], 제거"
  - "파일[C++], 임시"
  - "임시 파일 제거"
  - "rmtmp 함수"
  - "임시 파일[C++], 제거"
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rmtmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임시 파일을 제거합니다.  
  
## 구문  
  
```  
  
int _rmtmp( void );  
```  
  
## 반환 값  
 `_rmtmp`는 닫히고 삭제된 임시 파일의 숫자를 반환합니다.  
  
## 설명  
 `_rmtmp` 함수는 현재 디렉터리의 모든 임시 파일을 정리합니다.  이 함수는 `tmpfile`에 의해서 생성된 파일만 제거합니다. 임시 파일이 생성된 디렉터리가 같은 디렉터리일 때에만 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_rmtmp`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)