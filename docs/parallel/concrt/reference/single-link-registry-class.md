---
title: "single_link_registry 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::single_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_link_registry 클래스"
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# single_link_registry 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`single_link_registry` 개체는 단일 소스 블록 또는 대상 블록만 관리하는 `network_link_registry`입니다.  
  
## 구문  
  
```  
template<  
   class _Block  
>  
class single_link_registry : public network_link_registry<_Block>;  
```  
  
#### 매개 변수  
 `_Block`  
 `single_link_registry` 개체에 저장되는 블록 데이터 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[single\_link\_registry::single\_link\_registry 생성자](../Topic/single_link_registry::single_link_registry%20Constructor.md)|`single_link_registry` 개체를 생성합니다.|  
|[single\_link\_registry::~single\_link\_registry 소멸자](../Topic/single_link_registry::~single_link_registry%20Destructor.md)|`single_link_registry` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[single\_link\_registry::add 메서드](../Topic/single_link_registry::add%20Method.md)|`single_link_registry` 개체에 링크를 추가합니다. \([network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md)를 재정의합니다.\)|  
|[single\_link\_registry::begin 메서드](../Topic/single_link_registry::begin%20Method.md)|`single_link_registry` 개체에서 첫 번째 요소에 대한 반복기를 반환합니다. \([network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md)를 재정의합니다.\)|  
|[single\_link\_registry::contains 메서드](../Topic/single_link_registry::contains%20Method.md)|지정된 블록에 대해 `single_link_registry` 개체를 검색합니다. \([network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md)를 재정의합니다.\)|  
|[single\_link\_registry::count 메서드](../Topic/single_link_registry::count%20Method.md)|`single_link_registry` 개체의 항목 수를 카운트합니다. \([network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md)를 재정의합니다.\)|  
|[single\_link\_registry::remove 메서드](../Topic/single_link_registry::remove%20Method.md)|`single_link_registry` 개체에서 링크를 제거합니다. \([network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md)를 재정의합니다.\)|  
  
## 상속 계층  
 [network\_link\_registry](../../../parallel/concrt/reference/network-link-registry-class.md)  
  
 `single_link_registry`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [multi\_link\_registry 클래스](../../../parallel/concrt/reference/multi-link-registry-class.md)