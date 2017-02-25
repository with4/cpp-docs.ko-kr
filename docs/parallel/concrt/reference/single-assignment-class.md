---
title: "single_assignment 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::single_assignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_assignment 클래스"
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# single_assignment 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`single_assignment` 메시징 블록은 단일, 한 번 쓰기 `message` 저장이 가능한 다중 대상, 다중 소스, 순서가 지정된 `propagator_block`입니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class single_assignment : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### 매개 변수  
 `_Type`  
 버퍼에 의해 저장되고 전파되는 메시지의 페이로드 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[single\_assignment::single\_assignment 생성자](../Topic/single_assignment::single_assignment%20Constructor.md)|오버로드됨.  `single_assignment` 메시징 블록을 생성합니다.|  
|[single\_assignment::~single\_assignment 소멸자](../Topic/single_assignment::~single_assignment%20Destructor.md)|`single_assignment` 메시징 블록을 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[single\_assignment::has\_value 메서드](../Topic/single_assignment::has_value%20Method.md)|이 `single_assignment` 메시징 블록이 값으로 초기화되었는지 여부를 확인합니다.|  
|[single\_assignment::value 메서드](../Topic/single_assignment::value%20Method.md)|`single_assignment` 메시징 블록에 저장되는 메시지의 현재 페이로드에 대한 참조를 가져옵니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[single\_assignment::accept\_message 메서드](../Topic/single_assignment::accept_message%20Method.md)|호출자에게 메시지의 사본을 반환하는 이 `single_assignment` 메시징 블록에 의해 제공된 메시지를 수락합니다.|  
|[single\_assignment::consume\_message 메서드](../Topic/single_assignment::consume_message%20Method.md)|`single_assignment`가 이전에 제공하고 메시지의 복사본을 호출자에게 반환하는 대상이 예약한 메시지를 사용합니다.|  
|[single\_assignment::link\_target\_notification 메서드](../Topic/single_assignment::link_target_notification%20Method.md)|새 대상이 이 `single_assignment` 메시징 블록에 연결되었음을 알리는 콜백입니다.|  
|[single\_assignment::propagate\_message 메서드](../Topic/single_assignment::propagate_message%20Method.md)|비동기적으로 메시지를 `ISource` 블록에서 이 `single_assignment` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[single\_assignment::propagate\_to\_any\_targets 메서드](../Topic/single_assignment::propagate_to_any_targets%20Method.md)|이 `single_assignment` 메시징 블록에 `message``_PMessage`를 배치하고 연결된 모든 대상에 제공합니다.|  
|[single\_assignment::release\_message 메서드](../Topic/single_assignment::release_message%20Method.md)|이전 메시지 예약을 해제합니다. \([source\_block::release\_message](../Topic/source_block::release_message%20Method.md)를 재정의합니다.\)|  
|[single\_assignment::reserve\_message 메서드](../Topic/single_assignment::reserve_message%20Method.md)|이 `single_assignment` 메시징 블록이 이전에 제공한 메시지를 예약합니다. \([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)를 재정의합니다.\)|  
|[single\_assignment::resume\_propagation 메서드](../Topic/single_assignment::resume_propagation%20Method.md)|예약이 해제된 후 전파를 다시 시작합니다. \([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)를 재정의합니다.\)|  
|[single\_assignment::send\_message 메서드](../Topic/single_assignment::send_message%20Method.md)|동기적으로 메시지를 이 `ISource` 블록에서 이 `single_assignment` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `send` 메서드가 호출됩니다.|  
  
## 설명  
 `single_assignment` 메시징 블록은 각 대상으로 메시지 복사본을 전파합니다.  
  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `single_assignment`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [overwrite\_buffer 클래스](../../../parallel/concrt/reference/overwrite-buffer-class.md)   
 [unbounded\_buffer 클래스](../Topic/unbounded_buffer%20Class.md)