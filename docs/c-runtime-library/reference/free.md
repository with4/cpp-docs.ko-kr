---
title: "free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "free"
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
  - "free"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 블록, 할당 해제"
  - "free 함수"
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

할당을 취소하거나 메모리 블록을 해제합니다.  
  
## 구문  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### 매개 변수  
 `memblock`  
 해제해야 할 이전에 할당된 메모리 블록입니다.  
  
## 설명  
 `free` 함수는 `calloc`, `malloc` 또는 `realloc`을 호출하여 이전에 할당된 메모리 블록\(`memblock`\)을 할당 해제합니다.  할당 해제된 바이트 수는 블록이 할당될 때 요구되는 바이트 수와 같습니다. \(혹은 재할당의 경우, `realloc`\)  `memblock`가 `NULL`이면, 포인터는 무시되고 `free`는 즉시 반환합니다.  잘못된 포인터\(`calloc`, `malloc` 또는 `realloc`에 의해 할당되지 않은 메모리 블록을 가리키는 포인터\)를 해제하려는 시도는 후속 할당 요청에 영향을 미치고 오류를 발생시킬 수 있습니다.  
  
 해제 된 메모리에 오류가 발생 하면  `errno` 는 오류의 성격에서 운영 체제의 정보로 설정됩니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 메모리 블록이 해제된 후, [\_heapmin](../../c-runtime-library/reference/heapmin.md)는 사용되지 않은 지역을 연합하고 운영 체제에게 이를 돌려줌으로써 힙에서의 메모리 해제의 양을 최소화합니다.  운영 체제에 반환되지 않은 해제된 메모리는 자유 풀에 재저장되며 재할당될 수 있습니다.  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `free`은 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)가 됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 `free` 는 `__declspec(noalias)` 로 표시됩니다, 함수는 전역 변수를 수정할 수는 없다는 것을 보장합니다.  더 자세한 내용은 [주석](../../cpp/noalias.md)을 참조하십시오.  
  
 [\_malloca](../../c-runtime-library/reference/malloca.md)를 사용하여 할당된 메모리를 해제하려면, [\_freea](../../c-runtime-library/reference/freea.md)를 사용합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`free`|\<stdlib.h\> 및 \<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [malloc](../../c-runtime-library/reference/malloc.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [\_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_freea](../../c-runtime-library/reference/freea.md)