---
title: "max_variable_size 클래스 | Microsoft Docs"
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
  - "stdext::max_variable_size"
  - "allocators/stdext::max_variable_size"
  - "stdext.max_variable_size"
  - "max_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_variable_size 클래스"
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_variable_size 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명는 [클래스 최대](../standard-library/allocators-header.md) 개체를 제한 하는 [freelist](../standard-library/freelist-class.md) 개체의 수에 비례하여 대략적으로 최대 길이를 메모리 블록을 할당 합니다.  
  
## 구문  
  
```  
class max_variable_size  
```  
  
### 생성자  
  
|||  
|-|-|  
|[max\_variable\_size](../Topic/max_variable_size::max_variable_size.md)|`max_variable_size` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/max_variable_size::allocated.md)|할당 된 메모리 블록의 수를 증가 시킵니다.|  
|[할당 취소](../Topic/max_variable_size::deallocated.md)|감소의 수는 메모리 블록을 할당합니다.|  
|[전체](../Topic/max_variable_size::full.md)|더 많은 메모리 블록을 가능한 목록에 추가할지 여부를 지정 하는 값을 반환 합니다.|  
|[출시](../Topic/max_variable_size::released.md)|가능한 목록에 차단 메모리의 수를 감소 시킵니다.|  
|[저장](../Topic/max_variable_size::saved.md)|가능한 목록에 대 한 메모리 블록의 수를 증가 시킵니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)