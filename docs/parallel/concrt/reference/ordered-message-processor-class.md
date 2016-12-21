---
title: "ordered_message_processor 클래스 | Microsoft Docs"
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
  - "agents/concurrency::ordered_message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered_message_processor 클래스"
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ordered_message_processor 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`ordered_message_processor`는 메시지 블록이 받은 순서대로 메시지를 처리할 수 있는 `message_processor`입니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class ordered_message_processor : public message_processor<_Type>;  
```  
  
#### 매개 변수  
 `_Type`  
 프로세서에 의해 처리되는 메시지의 페이로드 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`type`|`_Type`에 대한 형식의 별칭입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ordered\_message\_processor::ordered\_message\_processor 생성자](../Topic/ordered_message_processor::ordered_message_processor%20Constructor.md)|`ordered_message_processor` 개체를 생성합니다.|  
|[ordered\_message\_processor::~ordered\_message\_processor 소멸자](../Topic/ordered_message_processor::~ordered_message_processor%20Destructor.md)|`ordered_message_processor` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ordered\_message\_processor::async\_send 메서드](../Topic/ordered_message_processor::async_send%20Method.md)|아직 수행되지 않은 경우 비동기적으로 메시지를 큐에 대기시키고 처리 작업을 시작합니다. \([message\_processor::async\_send](../Topic/message_processor::async_send%20Method.md)를 재정의합니다.\)|  
|[ordered\_message\_processor::initialize 메서드](../Topic/ordered_message_processor::initialize%20Method.md)|적절한 콜백 함수, 스케줄러 및 일정 그룹으로 `ordered_message_processor` 개체를 초기화합니다.|  
|[ordered\_message\_processor::initialize\_batched\_processing 메서드](../Topic/ordered_message_processor::initialize_batched_processing%20Method.md)|일관된 메시지 처리를 초기화합니다.|  
|[ordered\_message\_processor::sync\_send 메서드](../Topic/ordered_message_processor::sync_send%20Method.md)|동기적으로 메시지를 큐에 대기시키고 아직 시작하지 않은 경우 처리 작업을 시작합니다. \([message\_processor::sync\_send](../Topic/message_processor::sync_send%20Method.md)를 재정의합니다.\)|  
|[ordered\_message\_processor::wait 메서드](../Topic/ordered_message_processor::wait%20Method.md)|메시지 블록의 소멸자에 사용된 프로세서별 스핀 대기는 블록 소멸 전에 모든 비동기 처리 작업이 완료될 시간이 있는지 확인합니다. \([message\_processor::wait](../Topic/message_processor::wait%20Method.md)를 재정의합니다.\)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[ordered\_message\_processor::process\_incoming\_message 메서드](../Topic/ordered_message_processor::process_incoming_message%20Method.md)|비동기적으로 호출되는 처리 함수입니다.  메시지를 큐에서 제거하고 처리를 시작합니다. \([message\_processor::process\_incoming\_message](../Topic/message_processor::process_incoming_message%20Method.md)를 재정의합니다.\)|  
  
## 상속 계층  
 [message\_processor](../../../parallel/concrt/reference/message-processor-class.md)  
  
 `ordered_message_processor`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)