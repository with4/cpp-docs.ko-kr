---
title: "timer 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::timer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer 클래스"
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# timer 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`timer` 메시징 블록은 지정된 시간이 경과되거나 특정 간격으로 대상에 메시지를 보낼 수 있는 단일 대상 `source_block`입니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<_Type>>>;  
```  
  
#### 매개 변수  
 `_Type`  
 이 블록의 출력 메시지의 페이로드 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[timer::timer 생성자](../Topic/timer::timer%20Constructor.md)|오버로드됨.  지정된 간격 후에 주어진 메시지를 발생시키는 `timer` 메시징 블록을 생성합니다.|  
|[timer::~timer 소멸자](../Topic/timer::~timer%20Destructor.md)|`timer` 메시징 블록을 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[timer::pause 메서드](../Topic/timer::pause%20Method.md)|`timer` 메시징 블록을 중지합니다.  반복되는 `timer` 메시징 블록의 경우 후속 `start()` 호출로 다시 시작할 수 있습니다.  반복되지 않는 타이머의 경우 이것은 `stop` 호출과 같은 결과를 갖습니다.|  
|[timer::start 메서드](../Topic/timer::start%20Method.md)|`timer` 메시징 블록을 시작합니다.  호출된 후 지정된 시간\(밀리초\)으로 지정된 값은 `message`로 다운스트림에 전파됩니다.|  
|[timer::stop 메서드](../Topic/timer::stop%20Method.md)|`timer` 메시징 블록을 중지합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[timer::accept\_message 메서드](../Topic/timer::accept_message%20Method.md)|호출자에게 소유권을 전송하는 이 `timer` 메시징 블록에 의해 제공된 메시지를 수락합니다.|  
|[timer::consume\_message 메서드](../Topic/timer::consume_message%20Method.md)|`timer`가 이전에 제공하고 호출자에게 소유권을 전송하는 대상이 예약한 메시지를 생성합니다.|  
|[timer::link\_target\_notification 메서드](../Topic/timer::link_target_notification%20Method.md)|새 대상이 이 `timer` 메시징 블록에 연결되었음을 알리는 콜백입니다.|  
|[timer::propagate\_to\_any\_targets 메서드](../Topic/timer::propagate_to_any_targets%20Method.md)|모든 연결된 대상에 `timer` 블록에 의해 생성된 메시지를 제공하도록 시도합니다.|  
|[timer::release\_message 메서드](../Topic/timer::release_message%20Method.md)|이전 메시지 예약을 해제합니다. \([source\_block::release\_message](../Topic/source_block::release_message%20Method.md)를 재정의합니다.\)|  
|[timer::reserve\_message 메서드](../Topic/timer::reserve_message%20Method.md)|이 `timer` 메시징 블록이 이전에 제공한 메시지를 예약합니다. \([source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)를 재정의합니다.\)|  
|[timer::resume\_propagation 메서드](../Topic/timer::resume_propagation%20Method.md)|예약이 해제된 후 전파를 다시 시작합니다. \([source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)를 재정의합니다.\)|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `timer`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)