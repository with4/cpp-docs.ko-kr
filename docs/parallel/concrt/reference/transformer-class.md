---
title: "transformer 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::transformer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer 클래스"
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# transformer 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`transformer` 메시징 블록은 한 형식의 메시지를 수락할 수 있는 단일 대상, 다중 소스, 주문형 `propagator_block`이며 다른 형식의 제한되지 않은 수의 메시지를 저장할 수 있습니다.  
  
## 구문  
  
```  
template<  
   class _Input,  
   class _Output  
>  
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>, multi_link_registry<ISource<_Input>>>;  
```  
  
#### 매개 변수  
 `_Input`  
 버퍼에서 허용하는 메시지의 페이로드 형식입니다.  
  
 `_Output`  
 버퍼에 의해 저장되고 전파되는 메시지의 페이로드 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[transformer::transformer 생성자](../Topic/transformer::transformer%20Constructor.md)|오버로드됨.  `transformer` 메시징 블록을 생성합니다.|  
|[transformer::~transformer 소멸자](../Topic/transformer::~transformer%20Destructor.md)|`transformer` 메시징 블록을 소멸시킵니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[transformer::accept\_message 메서드](../Topic/transformer::accept_message%20Method.md)|호출자에게 소유권을 전송하는 이 `transformer` 메시징 블록에 의해 제공된 메시지를 수락합니다.|  
|[transformer::consume\_message 메서드](../Topic/transformer::consume_message%20Method.md)|`transformer`가 이전에 제공하고 호출자에게 소유권을 전송하는 대상이 예약한 메시지를 생성합니다.|  
|[transformer::link\_target\_notification 메서드](../Topic/transformer::link_target_notification%20Method.md)|새 대상이 이 `transformer` 메시징 블록에 연결되었음을 알리는 콜백입니다.|  
|[transformer::propagate\_message 메서드](../Topic/transformer::propagate_message%20Method.md)|비동기적으로 메시지를 `ISource` 블록에서 이 `transformer` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[transformer::propagate\_to\_any\_targets 메서드](../Topic/transformer::propagate_to_any_targets%20Method.md)|입력된 메시지에서 변환 함수를 실행합니다.|  
|[transformer::release\_message 메서드](../Topic/transformer::release_message%20Method.md)|이전 메시지 예약을 해제합니다. \([source\_block::release\_message](../Topic/source_block::release_message%20Method.md)를 재정의합니다.\)|  
|[transformer::reserve\_message 메서드](../Topic/transformer::reserve_message%20Method.md)|이 `transformer` 메시징 블록이 이전에 제공한 메시지를 예약합니다. \([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)를 재정의합니다.\)|  
|[transformer::resume\_propagation 메서드](../Topic/transformer::resume_propagation%20Method.md)|예약이 해제된 후 전파를 다시 시작합니다. \([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)를 재정의합니다.\)|  
|[transformer::send\_message 메서드](../Topic/transformer::send_message%20Method.md)|동기적으로 메시지를 이 `ISource` 블록에서 이 `transformer` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `send` 메서드가 호출됩니다.|  
|[transformer::supports\_anonymous\_source 메서드](../Topic/transformer::supports_anonymous_source%20Method.md)|`supports_anonymous_source`  메서드를 재정의하여 이 블록에 연결 되지 않은 소스에서 제공하는 메시지를 사용할 수 있도록 표시합니다. \(재정의  [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md).\)|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `transformer`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [call 클래스](../../../parallel/concrt/reference/call-class.md)