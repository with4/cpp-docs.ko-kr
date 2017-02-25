---
title: "target_block 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::target_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "target_block 클래스"
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# target_block 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`target_block` 클래스는 대상 블록에 대해서만 기본 링크 관리 기능 및 오류 검사 기능을 제공하는 추상화 기본 클래스입니다.  
  
## 구문  
  
```  
template<  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>  
>  
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### 매개 변수  
 `_SourceLinkRegistry`  
 소스 링크를 저장하는 데 사용할 링크 레지스트리입니다.  
  
 `_MessageProcessorType`  
 메시지 처리를 위한 프로세서 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`source_iterator`|이 `target_block` 개체에 대한 `source_link_manager`의 반복기 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[target\_block::target\_block 생성자](../Topic/target_block::target_block%20Constructor.md)|`target_block` 개체를 생성합니다.|  
|[target\_block::~target\_block 소멸자](../Topic/target_block::~target_block%20Destructor.md)|`target_block` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[target\_block::propagate 메서드](../Topic/target_block::propagate%20Method.md)|소스 블록에서 이 대상 블록에 메시지를 비동기적으로 전달합니다.|  
|[target\_block::send 메서드](../Topic/target_block::send%20Method.md)|소스 블록에서 이 대상 블록에 메시지를 동기적으로 전달합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[target\_block::async\_send 메서드](../Topic/target_block::async_send%20Method.md)|처리를 위한 메시지를 비동기적으로 보냅니다.|  
|[target\_block::decline\_incoming\_messages 메서드](../Topic/target_block::decline_incoming_messages%20Method.md)|새 메시지가 거부되어야 하는 블록을 나타냅니다.|  
|[target\_block::enable\_batched\_processing 메서드](../Topic/target_block::enable_batched_processing%20Method.md)|이 블록에 대한 일괄 처리를 할 수 ​​있도록합니다.|  
|[target\_block::initialize\_target 메서드](../Topic/target_block::initialize_target%20Method.md)|기본 개체를 초기화합니다.  특히, `message_processor` 개체를 초기화해야 합니다.|  
|[target\_block::link\_source 메서드](../Topic/target_block::link_source%20Method.md)|이 `target_block` 개체에 지정된 소스 블록을 연결합니다.|  
|[target\_block::process\_input\_messages 메서드](../Topic/target_block::process_input_messages%20Method.md)|입력으로 받은 메시지를 처리합니다.|  
|[target\_block::process\_message 메서드](../Topic/target_block::process_message%20Method.md)|파생 클래스에서 재정의된 경우, 이 `target_block` 개체가 수락했던 메시지를 처리합니다.|  
|[target\_block::propagate\_message 메서드](../Topic/target_block::propagate_message%20Method.md)|파생 클래스에서 재정의된 경우 이 메서드는 비동기적으로 메시지를 `ISource` 블록에서 이 `target_block` 개체를 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[target\_block::register\_filter 메서드](../Topic/target_block::register_filter%20Method.md)|받은 모든 메시지에 대해 호출될 필터 메서드를 등록합니다.|  
|[target\_block::remove\_sources 메서드](../Topic/target_block::remove_sources%20Method.md)|처리 중인 비동기 보내기 작업이 끝나기를 기다린 후 모든 소스 연결을 해제합니다.|  
|[target\_block::send\_message 메서드](../Topic/target_block::send_message%20Method.md)|파생 클래스에서 재정의된 경우 이 메서드를 동기적으로 메시지를 `ISource` 블록에서 이 `target_block` 개체를 전달합니다.  소스 블록에 의해 호출되면 `send` 메서드가 호출됩니다.|  
|[target\_block::sync\_send 메서드](../Topic/target_block::sync_send%20Method.md)|처리를 위한 메시지를 동기적으로 보냅니다.|  
|[target\_block::unlink\_source 메서드](../Topic/target_block::unlink_source%20Method.md)|이 `target_block` 개체에서 지정한 소스 블록의 연결을 해제합니다.|  
|[target\_block::unlink\_sources 메서드](../Topic/target_block::unlink_sources%20Method.md)|이 `target_block` 개체에서 모든 소스 블록의 연결을 해제합니다. \([ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md)를 재정의합니다.\)|  
|[target\_block::wait\_for\_async\_sends 메서드](../Topic/target_block::wait_for_async_sends%20Method.md)|모든 비동기 전파가 완료되기를 기다립니다.|  
  
## 상속 계층  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 `target_block`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget 클래스](../../../parallel/concrt/reference/itarget-class.md)