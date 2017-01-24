---
title: "join 클래스 | Microsoft Docs"
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
  - "agents/concurrency::join"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "join 클래스"
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# join 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`join` 메시징 블록은 각 소스에서 형식 `_Type`의 메시지를 결합하는 단일 대상, 다중 소스, 순서형 `propagator_block`입니다.  
  
## 구문  
  
```  
template<  
   class _Type,  
   join_type _Jtype = non_greedy  
>  
class join : public propagator_block<single_link_registry<ITarget<std::vector<_Type>>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### 매개 변수  
 `_Type`  
 블록에 의해 조인되고 전파되는 메시지의 페이로드 형식입니다.  
  
 `_Jtype`  
 `greedy` 또는 `non_greedy`의 `join` 블록 종류입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[join::join 생성자](../Topic/join::join%20Constructor.md)|오버로드됨.  `join` 메시징 블록을 생성합니다.|  
|[join::~join 소멸자](../Topic/join::~join%20Destructor.md)|`join` 블록을 소멸시킵니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[join::accept\_message 메서드](../Topic/join::accept_message%20Method.md)|호출자에게 소유권을 전송하는 이 `join` 메시징 블록에 의해 제공된 메시지를 수락합니다.|  
|[join::consume\_message 메서드](../Topic/join::consume_message%20Method.md)|`join` 메시징 블록이 이전에 제공하고 호출자에게 소유권을 전송하는 대상이 예약한 메시지를 생성합니다.|  
|[join::link\_target\_notification 메서드](../Topic/join::link_target_notification%20Method.md)|새 대상이 이 `join` 메시징 블록에 연결되었음을 알리는 콜백입니다.|  
|[join::propagate\_message 메서드](../Topic/join::propagate_message%20Method.md)|비동기적으로 메시지를 `ISource` 블록에서 이 `join` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[join::propagate\_to\_any\_targets 메서드](../Topic/join::propagate_to_any_targets%20Method.md)|모든 메시지가 전파되면 각 소스에서 입력 메시지가 들어 있는 출력 메시지를 생성합니다.  각 대상에 이 출력 메시지를 보냅니다.|  
|[join::release\_message 메서드](../Topic/join::release_message%20Method.md)|이전 메시지 예약을 해제합니다. \([source\_block::release\_message](../Topic/source_block::release_message%20Method.md)를 재정의합니다.\)|  
|[join::reserve\_message 메서드](../Topic/join::reserve_message%20Method.md)|이 `join` 메시징 블록이 이전에 제공한 메시지를 예약합니다. \([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)를 재정의합니다.\)|  
|[join::resume\_propagation 메서드](../Topic/join::resume_propagation%20Method.md)|예약이 해제된 후 전파를 다시 시작합니다. \([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)를 재정의합니다.\)|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `join`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [choice 클래스](../../../parallel/concrt/reference/choice-class.md)   
 [multitype\_join 클래스](../../../parallel/concrt/reference/multitype-join-class.md)   
 [join\_type 열거형](../Topic/join_type%20Enumeration.md)