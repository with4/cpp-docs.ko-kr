---
title: "_msize | Microsoft Docs"
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
  - "_msize"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "msize"
  - "_msize"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_msize 함수"
  - "메모리 블록"
  - "msize 함수"
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _msize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙에 할당 된 메모리 블록의 크기를 반환 합니다.  
  
## 구문  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### 매개 변수  
 `memblock`  
 메모리 블록에 대한 포인터입니다.  
  
## 반환 값  
 `_msize` 는 부호 없는 정수 크기 \(바이트\)를 반환합니다.  
  
## 설명  
 `_msize` 함수는 `calloc`, `malloc`, 또는 `realloc` 를 호출하여 할당된 메모리 블록의 바이트에서 크기를 반환합니다.  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `_msize`은 [\_msize\_dbg](../../c-runtime-library/reference/msize-dbg.md)가 됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 이 함수는 매개변수를 인증합니다.  [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)이 널 포인터일 경우, `_msize`에 설명된 대로, `memblock`는 잘못된 매개 변수 처리기를 호출합니다.  오류가 처리가된 경우, 함수는 `errno` 을 `EINVAL` 으로 설정하고, \-1을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_msize`|\<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 [realloc](../../c-runtime-library/reference/realloc.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)