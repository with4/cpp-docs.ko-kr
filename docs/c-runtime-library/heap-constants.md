---
title: "힙 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HEAPBADPTR"
  - "_HEAPEMPTY"
  - "_HEAPBADBEGIN"
  - "_HEAPOK"
  - "_HEAPBADNODE"
  - "_HEAPEND"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HEAPBADBEGIN 상수"
  - "_HEAPBADNODE 상수"
  - "_HEAPBADPTR 상수"
  - "_HEAPEMPTY 상수"
  - "_HEAPEND 상수"
  - "_HEAPOK 상수"
  - "힙 상수"
  - "HEAPBADBEGIN 상수"
  - "HEAPBADNODE 상수"
  - "HEAPBADPTR 상수"
  - "HEAPEMPTY 상수"
  - "HEAPEND 상수"
  - "HEAPOK 상수"
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 힙 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <malloc.h>  
  
```  
  
## 설명  
 이러한 상수는 힙의 상태를 나타내는 반환 값을 제공 합니다.  
  
|상수|의미|  
|--------|--------|  
|`_HEAPBADBEGIN`|초기 헤더 정보를 찾을 수 없거나 올바르지 않습니다.|  
|`_HEAPBADNODE`|잘못 된 노드를 찾을 수 없거나 또는 힙이 손상 되었습니다.|  
|`_HEAPBADPTR`|**\_HEAPINFO** 구조체의 **\_pentry** 필드는 힙에 유효한 포인터를 가지지 않습니다.\(`_heapwalk` 루틴에만 해당\)|  
|`_HEAPEMPTY`|힙이 초기화되지 않았습니다.|  
|`_HEAPEND`|힙 끝에 성공적으로 도달 했습니다 \(`_heapwalk` 루틴에만 해당\).|  
|`_HEAPOK`|힙이 일치합니다 \(`_heapset` 및 `_heapchk` 루틴에만 해당\)  오류까지. **\_HEAPINFO** 구조체는 다음 항목에 대한 정보를 포함합니다. \(`_heapwalk` 루틴에만 해당\).|  
  
## 참고 항목  
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [전역 상수](../c-runtime-library/global-constants.md)