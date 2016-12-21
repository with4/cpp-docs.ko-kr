---
title: "source_link_manager 클래스 | Microsoft Docs"
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
  - "agents/concurrency::source_link_manager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_link_manager 클래스"
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# source_link_manager 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`source_link_manager` 개체는 `ISource` 블록에 대한 메시징 블록 네트워크 링크를 관리합니다.  
  
## 구문  
  
```  
template<  
   class _LinkRegistry  
>  
class source_link_manager;  
```  
  
#### 매개 변수  
 `_LinkRegistry`  
 네트워크 연결 레지스트리입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`const_pointer`|`source_link_manager` 개체에서 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|`const_reference`|const 작업을 읽고 수행하기 위해 `source_link_manager` 개체에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|`iterator`|`source_link_manager` 개체에 있는 모든 요소를 읽거나 수정할 수 있는 반복기를 제공하는 형식입니다.|  
|`type`|`source_link_manager` 개체에 의해 관리되는 링크 레지스트리의 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[source\_link\_manager::source\_link\_manager 생성자](../Topic/source_link_manager::source_link_manager%20Constructor.md)|`source_link_manager` 개체를 생성합니다.|  
|[source\_link\_manager::~source\_link\_manager 소멸자](../Topic/source_link_manager::~source_link_manager%20Destructor.md)|`source_link_manager` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[source\_link\_manager::add 메서드](../Topic/source_link_manager::add%20Method.md)|`source_link_manager` 개체에 소스 링크를 추가합니다.|  
|[source\_link\_manager::begin 메서드](../Topic/source_link_manager::begin%20Method.md)|`source_link_manager` 개체에서 첫 번째 요소에 대한 반복기를 반환합니다.|  
|[source\_link\_manager::contains 메서드](../Topic/source_link_manager::contains%20Method.md)|지정된 블록에 대해 이 `source_link_manager` 내에서 `network_link_registry`를 검색합니다.|  
|[source\_link\_manager::count 메서드](../Topic/source_link_manager::count%20Method.md)|`source_link_manager` 개체에 연결된 블록 수를 셉니다.|  
|[source\_link\_manager::reference 메서드](../Topic/source_link_manager::reference%20Method.md)|`source_link_manager` 개체에 대한 참조를 가져옵니다.|  
|[source\_link\_manager::register\_target\_block 메서드](../Topic/source_link_manager::register_target_block%20Method.md)|`source_link_manager` 개체를 저장할 대상 블록을 등록합니다.|  
|[source\_link\_manager::release 메서드](../Topic/source_link_manager::release%20Method.md)|`source_link_manager` 개체에서 참조를 해제합니다.|  
|[source\_link\_manager::remove 메서드](../Topic/source_link_manager::remove%20Method.md)|`source_link_manager` 개체에서 링크를 제거합니다.|  
|[source\_link\_manager::set\_bound 메서드](../Topic/source_link_manager::set_bound%20Method.md)|이 `source_link_manager` 개체에 추가할 수 있는 소스 링크의 최대 수를 설정합니다.|  
  
## 설명  
 현재 소스 블록은 참조를 계산하지 않습니다.  이는 링크에 대한 동시 액세스를 허용하고 콜백을 통해 링크를 참조하는 기능을 제공하는 `network_link_registry` 개체의 래퍼입니다.  메시지 블록 \(`target_block`s 또는 `propagator_block` s\)은 소스 연결을 위해 이 클래스를 사용해야 합니다.  
  
## 상속 계층  
 `source_link_manager`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry 클래스](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry 클래스](../../../parallel/concrt/reference/multi-link-registry-class.md)