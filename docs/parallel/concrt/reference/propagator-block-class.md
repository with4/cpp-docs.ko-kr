---
title: "propagator_block 클래스 | Microsoft Docs"
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
  - "agents/concurrency::propagator_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propagator_block 클래스"
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propagator_block 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`propagator_block` 클래스는 소스 및 대상인 메시지 블록에 대한 추상 기본 클래스입니다.  `source_block` 및 `target_block` 클래스의 기능을 결합합니다.  
  
## 구문  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class propagator_block : public source_block<_TargetLinkRegistry, _MessageProcessorType>, public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### 매개 변수  
 `_TargetLinkRegistry`  
 대상 링크를 저장하는 데 사용할 링크 레지스트리입니다.  
  
 `_SourceLinkRegistry`  
 소스 링크를 저장하는 데 사용할 링크 레지스트리입니다.  
  
 `_MessageProcessorType`  
 메시지 처리를 위한 프로세서 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`source_iterator`|이 `propagator_block`에 대한 `source_link_manager`의 반복기 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[propagator\_block::propagator\_block 생성자](../Topic/propagator_block::propagator_block%20Constructor.md)|`propagator_block` 개체를 생성합니다.|  
|[propagator\_block::~propagator\_block 소멸자](../Topic/propagator_block::~propagator_block%20Destructor.md)|`propagator_block` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[propagator\_block::propagate 메서드](../Topic/propagator_block::propagate%20Method.md)|소스 블록에서 이 대상 블록에 메시지를 비동기적으로 전달합니다.|  
|[propagator\_block::send 메서드](../Topic/propagator_block::send%20Method.md)|이 블록에 대한 메시지를 동기적으로 시작합니다.  `ISource` 블록에 의해 호출됩니다.  이 함수가 완료되면 메시지는 이미 블록 안으로 전파되어 있습니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[propagator\_block::decline\_incoming\_messages 메서드](../Topic/propagator_block::decline_incoming_messages%20Method.md)|새 메시지가 거부되어야 하는 블록을 나타냅니다.|  
|[propagator\_block::initialize\_source\_and\_target 메서드](../Topic/propagator_block::initialize_source_and_target%20Method.md)|기본 개체를 초기화합니다.  특히, `message_processor` 개체를 초기화해야 합니다.|  
|[propagator\_block::link\_source 메서드](../Topic/propagator_block::link_source%20Method.md)|이 `propagator_block` 개체에 지정된 소스 블록을 연결합니다.|  
|[propagator\_block::process\_input\_messages 메서드](../Topic/propagator_block::process_input_messages%20Method.md)|입력된 메시지를 처리합니다.  Source\_block\(재정의  [source\_block::process\_input\_messages](../Topic/source_block::process_input_messages%20Method.md).\)에서 파생 하는 전파자 블록 에서만 유효합니다.|  
|[propagator\_block::propagate\_message 메서드](../Topic/propagator_block::propagate_message%20Method.md)|파생 클래스에서 재정의된 경우 이 메서드는 비동기적으로 메시지를 `ISource` 블록에서 이 `propagator_block` 개체를 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[propagator\_block::register\_filter 메서드](../Topic/propagator_block::register_filter%20Method.md)|받은 모든 메시지에 대해 호출될 필터 메서드를 등록합니다.|  
|[propagator\_block::remove\_network\_links 메서드](../Topic/propagator_block::remove_network_links%20Method.md)|이 `propagator_block` 개체에서 모든 소스 및 대상 네트워크 링크를 제거합니다.|  
|[propagator\_block::send\_message 메서드](../Topic/propagator_block::send_message%20Method.md)|파생 클래스에서 재정의된 경우 이 메서드를 동기적으로 메시지를 `ISource` 블록에서 이 `propagator_block` 개체를 전달합니다.  소스 블록에 의해 호출되면 `send` 메서드가 호출됩니다.|  
|[propagator\_block::unlink\_source 메서드](../Topic/propagator_block::unlink_source%20Method.md)|이 `propagator_block` 개체에서 지정한 소스 블록의 연결을 해제합니다.|  
|[propagator\_block::unlink\_sources 메서드](../Topic/propagator_block::unlink_sources%20Method.md)|이 `propagator_block` 개체에서 모든 소스 블록의 연결을 해제합니다. \([ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md)를 재정의합니다.\)|  
  
## 설명  
 다중 상속이 발생하지 않도록 `propagator_block` 클래스는 `source_block` 클래스 및 `ITarget` 추상 클래스에서 상속됩니다.  `target_block` 클래스의 기능 대부분은 여기에 복제됩니다.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `propagator_block`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [source\_block 클래스](../../../parallel/concrt/reference/source-block-class.md)   
 [ITarget 클래스](../../../parallel/concrt/reference/itarget-class.md)