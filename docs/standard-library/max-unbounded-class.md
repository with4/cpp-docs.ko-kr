---
title: "max_unbounded 클래스 | Microsoft Docs"
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
  - "allocators/stdext::max_unbounded"
  - "stdext::max_unbounded"
  - "stdext.max_unbounded"
  - "max_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_unbounded 클래스"
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_unbounded 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명는 [클래스 최대](../standard-library/allocators-header.md) 의 최대 길이 제한 하지 않는 개체는 [freelist](../standard-library/freelist-class.md) 개체입니다.  
  
## 구문  
  
```  
class max_unbounded  
```  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/max_unbounded::allocated.md)|할당 된 메모리 블록의 수를 증가 시킵니다.|  
|[할당 취소](../Topic/max_unbounded::deallocated.md)|감소의 수는 메모리 블록을 할당합니다.|  
|[전체](../Topic/max_unbounded::full.md)|더 많은 메모리 블록을 가능한 목록에 추가할지 여부를 지정 하는 값을 반환 합니다.|  
|[출시](../Topic/max_unbounded::released.md)|가능한 목록에 차단 메모리의 수를 감소 시킵니다.|  
|[저장](../Topic/max_unbounded::saved.md)|가능한 목록에 대 한 메모리 블록의 수를 증가 시킵니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)