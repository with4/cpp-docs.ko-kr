---
title: "message_processor 클래스 | Microsoft Docs"
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
  - "agents/concurrency::message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_processor 클래스"
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# message_processor 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`message_processor` 클래스는 `message` 개체의 처리를 위한 추상 기본 클래스입니다.  메시지 순서는 보장이 없습니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class message_processor;  
```  
  
#### 매개 변수  
 `_Type`  
 이 `message_processor` 개체에 의해 처리된 메시지 내의 페이로드 데이터 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`type`|`_Type`에 대한 형식의 별칭입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[message\_processor::async\_send 메서드](../Topic/message_processor::async_send%20Method.md)|파생 클래스에서 재정의된 경우 메시지를 비동기적으로 블록 안으로 넣습니다.|  
|[message\_processor::sync\_send 메서드](../Topic/message_processor::sync_send%20Method.md)|파생 클래스에서 재정의된 경우 메시지를 동기적으로 블록 안으로 넣습니다.|  
|[message\_processor::wait 메서드](../Topic/message_processor::wait%20Method.md)|파생 클래스에서 재정의된 경우 모든 비동기 작업이 완료될 때까지 기다립니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[message\_processor::process\_incoming\_message 메서드](../Topic/message_processor::process_incoming_message%20Method.md)|파생 클래스에서 재정의된 경우 블록에 대해 메시지의 순방향 처리를 수행합니다.  새 메시지가 추가되고 큐가 비어 있는 것이 발견될 때마다 한 번씩 호출됩니다.|  
  
## 상속 계층  
 `message_processor`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ordered\_message\_processor 클래스](../../../parallel/concrt/reference/ordered-message-processor-class.md)