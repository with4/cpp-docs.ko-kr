---
title: "데이터 맞춤 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data.alignment"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "데이터 맞춤[C++]"
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 데이터 맞춤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음과 같은 C 런타임 함수는 데이터 정렬을 지원합니다.  
  
### 데이터 정렬 루틴  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[\_aligned\_free](../c-runtime-library/reference/aligned-free.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) 을 사용하여 할당된 메모리 블록을 해제합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_free\_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|이러한 [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)으로 할당된 메모리 블록을 해제합니다.\(디버그 전용\)|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)|지정 된 맞춤 경계에 메모리를 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_malloc\_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|디버깅 헤더에 추가 공간을 사용 하여 지정 된 맞춤 경계에 메모리를 할당 하고 버퍼 \(디버그 버전에만 해당\)를 덮어씁니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_msize](../c-runtime-library/reference/aligned-msize.md)|힙에 할당 된 메모리 블록의 크기를 반환 합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_msize\_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|힙에 할당 된 메모리 블록의 크기를 반환합니다.\(디버그 버전에만 해당\)|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|지정 된 맞춤 경계에 메모리를 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_malloc\_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|지정 된 맞춤 경계 \(디버그 버전에만 해당\)에서 메모리를 할당합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(디버그 버전만 해당\)로 할당된 블록 메모리의 사이즈를 변경합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_realloc\_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(디버그 버전만 해당\)로 할당된 블록 메모리의 사이즈를 변경합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) 을 사용하여 할당된 메모리 블럭의 크기를 변경하고 메모리를 0으로 초기화합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_offset\_recalloc\_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) 를 사용하여 할당된 메모리 블럭의 크기를 변경하고 메모리를 0으로 초기화합니다\(디버그 버전에만 해당\)|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_realloc](../c-runtime-library/reference/aligned-realloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(디버그 버전만 해당\)로 할당된 블록 메모리의 사이즈를 변경합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_realloc\_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(디버그 버전만 해당\)로 할당된 블록 메모리의 사이즈를 변경합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) 을 사용하여 할당된 메모리 블럭의 크기를 변경하고 메모리를 0으로 초기화합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_aligned\_recalloc\_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) 를 사용하여 할당된 메모리 블럭의 크기를 변경하고 메모리를 0으로 초기화합니다\(디버그 버전에만 해당\)|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)