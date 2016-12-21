---
title: "source_block 클래스 | Microsoft Docs"
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
  - "agents/concurrency::source_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_block 클래스"
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# source_block 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`source_block` 클래스는 소스 전용 블록을 위한 추상 기본 클래스입니다.  클래스는 기본 링크 관리 기능은 물론 일반적인 오류 검사를 제공합니다.  
  
## 구문  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;  
```  
  
#### 매개 변수  
 `_TargetLinkRegistry`  
 대상 링크를 저장하는 데 사용할 링크 레지스트리입니다.  
  
 `_MessageProcessorType`  
 메시지 처리를 위한 프로세서 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`target_iterator`|연결된 대상을 탐색하는 반복기입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[source\_block::source\_block 생성자](../Topic/source_block::source_block%20Constructor.md)|`source_block` 개체를 생성합니다.|  
|[source\_block::~source\_block 소멸자](../Topic/source_block::~source_block%20Destructor.md)|`source_block` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[source\_block::accept 메서드](../Topic/source_block::accept%20Method.md)|호출자에게 소유권을 전송하는 이 `source_block` 개체에 의해 제공된 메시지를 수락합니다.|  
|[source\_block::acquire\_ref 메서드](../Topic/source_block::acquire_ref%20Method.md)|삭제가 발생하지 않도록 이 `source_block` 개체에서 참조 횟수를 가져옵니다.|  
|[source\_block::consume 메서드](../Topic/source_block::consume%20Method.md)|이 `source_block` 개체가 이전에 제공하고 호출자에게 소유권을 전송하는 대상이 성공적으로 예약한 메시지를 생성합니다.|  
|[source\_block::link\_target 메서드](../Topic/source_block::link_target%20Method.md)|이 `source_block` 개체에 대상 블록을 연결합니다.|  
|[source\_block::release 메서드](../Topic/source_block::release%20Method.md)|이전의 성공적인 메시지 예약을 해제합니다.|  
|[source\_block::release\_ref 메서드](../Topic/source_block::release_ref%20Method.md)|이 `source_block` 개체에서 참조 횟수를 해제합니다.|  
|[source\_block::reserve 메서드](../Topic/source_block::reserve%20Method.md)|이 `source_block` 개체가 이전에 제공한 메시지를 예약합니다.|  
|[source\_block::unlink\_target 메서드](../Topic/source_block::unlink_target%20Method.md)|이 `source_block` 개체에서 대상 블록을 연결 해제합니다.|  
|[source\_block::unlink\_targets 메서드](../Topic/source_block::unlink_targets%20Method.md)|이 `source_block` 개체에서 모든 대상 블록의 연결을 해제합니다. \([ISource::unlink\_targets](../Topic/ISource::unlink_targets%20Method.md)를 재정의합니다.\)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[source\_block::accept\_message 메서드](../Topic/source_block::accept_message%20Method.md)|파생 클래스에서 재정의된 경우 소스에서 제공한 메시지를 수락합니다.  메시지 블록은 `_MsgId`를 확인하고 메시지를 반환하도록 이 메서드를 재정의해야 합니다.|  
|[source\_block::async\_send 메서드](../Topic/source_block::async_send%20Method.md)|비동기적으로 메시지를 큐에 대기시키고 아직 시작하지 않은 경우 전파 작업을 시작합니다.|  
|[source\_block::consume\_message 메서드](../Topic/source_block::consume_message%20Method.md)|파생 클래스에서 재정의된 경우 이전에 예약한 메시지를 사용합니다.|  
|[source\_block::enable\_batched\_processing 메서드](../Topic/source_block::enable_batched_processing%20Method.md)|이 블록에 대한 일괄 처리를 할 수 ​​있도록합니다.|  
|[source\_block::initialize\_source 메서드](../Topic/source_block::initialize_source%20Method.md)|이 `source_block` 내에서 `message_propagator`를 초기화합니다.|  
|[source\_block::link\_target\_notification 메서드](../Topic/source_block::link_target_notification%20Method.md)|새 대상이 이 `source_block` 개체에 연결되었음을 알리는 콜백입니다.|  
|[source\_block::process\_input\_messages 메서드](../Topic/source_block::process_input_messages%20Method.md)|입력된 메시지를 처리합니다.  Source\_block에서 파생하는 전파자 블록에서만 유효합니다.|  
|[source\_block::propagate\_output\_messages 메서드](../Topic/source_block::propagate_output_messages%20Method.md)|메시지를 대상으로 전파합니다.|  
|[source\_block::propagate\_to\_any\_targets 메서드](../Topic/source_block::propagate_to_any_targets%20Method.md)|파생된 클래스에서 재정의될 때 모든 연결된 대상에 해당 메시지를 전파합니다.  메시지 블록에 대한 주 전파 루틴입니다.|  
|[source\_block::release\_message 메서드](../Topic/source_block::release_message%20Method.md)|파생 클래스에서 재정의된 경우 이전 메시지 예약을 해제합니다.|  
|[source\_block::remove\_targets 메서드](../Topic/source_block::remove_targets%20Method.md)|이 소스 블록의 모든 대상 링크를 제거합니다.  이는 소멸자에서 호출해야 합니다.|  
|[source\_block::reserve\_message 메서드](../Topic/source_block::reserve_message%20Method.md)|파생 클래스에서 재정의된 경우 이전에 이 `source_block` 블록에서 제공했던 메시지를 예약합니다.|  
|[source\_block::resume\_propagation 메서드](../Topic/source_block::resume_propagation%20Method.md)|파생 클래스에서 재정의된 경우 예약이 해제된 후 전파를 다시 시작합니다.|  
|[source\_block::sync\_send 메서드](../Topic/source_block::sync_send%20Method.md)|동기적으로 메시지를 큐에 대기시키고 아직 시작하지 않은 경우 전파 작업을 시작합니다.|  
|[source\_block::unlink\_target\_notification 메서드](../Topic/source_block::unlink_target_notification%20Method.md)|대상이 이 `source_block` 개체에서 연결이 끊어졌음을 알리는 콜백입니다.|  
|[source\_block::wait\_for\_outstanding\_async\_sends 메서드](../Topic/source_block::wait_for_outstanding_async_sends%20Method.md)|모든 비동기 전파가 완료되기를 기다립니다.  propagator 특정 스핀은 메시지 블록의 소멸자에 사용되어 블록 소멸 전에 모든 비동기 전파가 완료될 시간이 있는지 확인합니다.|  
  
## 설명  
 메시지 블록은 이 클래스에서 제공하는 연결 관리와 동기화를 이용하기 위해 이 블록에서 파생되어야 합니다.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `source_block`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource 클래스](../../../parallel/concrt/reference/isource-class.md)