---
title: "network_link_registry 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::network_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "network_link_registry 클래스"
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# network_link_registry 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`network_link_registry` 추상 기본 클래스는 소스 및 대상 블록 간의 링크를 관리합니다.  
  
## 구문  
  
```  
template<  
   class _Block  
>  
class network_link_registry;  
```  
  
#### 매개 변수  
 `_Block`  
 `network_link_registry`에 저장되는 블록 데이터 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`const_pointer`|`network_link_registry` 개체에서 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|`const_reference`|const 작업을 읽고 수행하기 위해 `network_link_registry` 개체에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|`iterator`|`network_link_registry` 개체에 있는 모든 요소를 읽거나 수정할 수 있는 반복기를 제공하는 형식입니다.|  
|`type`|`network_link_registry` 개체에 저장된 블록 형식을 나타내는 형식입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[network\_link\_registry::add 메서드](../Topic/network_link_registry::add%20Method.md)|파생 클래스에서 재정의되면 링크를 `network_link_registry` 개체에 추가합니다.|  
|[network\_link\_registry::begin 메서드](../Topic/network_link_registry::begin%20Method.md)|파생 클래스에서 재정의된 경우 `network_link_registry` 개체에 있는 첫 번째 요소의 반복기를 반환합니다.|  
|[network\_link\_registry::contains 메서드](../Topic/network_link_registry::contains%20Method.md)|파생 클래스에서 재정의된 경우 지정된 블록에 대한 `network_link_registry` 개체를 검색합니다.|  
|[network\_link\_registry::count 메서드](../Topic/network_link_registry::count%20Method.md)|파생 클래스에서 재정의된 경우 `network_link_registry` 개체에서 항목의 수를 반환합니다.|  
|[network\_link\_registry::remove 메서드](../Topic/network_link_registry::remove%20Method.md)|파생된 클래스에서 재정의하는 경우 지정된 블록을 `network_link_registry` 개체에서 제거합니다.|  
  
## 설명  
 `network link registry`는 동시 액세스에 안전하지 않습니다.  
  
## 상속 계층  
 `network_link_registry`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry 클래스](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry 클래스](../../../parallel/concrt/reference/multi-link-registry-class.md)