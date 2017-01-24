---
title: "max_none 클래스 | Microsoft Docs"
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
  - "max_none"
  - "stdext::max_none"
  - "stdext.max_none"
  - "allocators/stdext::max_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_none 클래스"
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_none 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명는 [클래스 최대](../standard-library/allocators-header.md) 개체를 제한 하는 [freelist](../standard-library/freelist-class.md) 개체 최대 길이가 0입니다.  
  
## 구문  
  
```  
template <std::size_t Max> class max_none  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Max`|에 저장할 수 있는 요소의 최대 수를 결정 하는 최대 클래스는 `freelist`합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/max_none::allocated.md)|할당 된 메모리 블록의 수를 증가 시킵니다.|  
|[할당 취소](../Topic/max_none::deallocated.md)|감소의 수는 메모리 블록을 할당합니다.|  
|[전체](../Topic/max_none::full.md)|더 많은 메모리 블록을 가능한 목록에 추가할지 여부를 지정 하는 값을 반환 합니다.|  
|[출시](../Topic/max_none::released.md)|가능한 목록에 차단 메모리의 수를 감소 시킵니다.|  
|[저장](../Topic/max_none::saved.md)|가능한 목록에 대 한 메모리 블록의 수를 증가 시킵니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)