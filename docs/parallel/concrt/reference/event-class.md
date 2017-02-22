---
title: "event 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 클래스"
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# event 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임을 명시적으로 인식하는 수동 재설정 이벤트입니다.  
  
## 구문  
  
```  
class event;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[event::~event 소멸자](../Topic/event::~event%20Destructor.md)|이벤트를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[event::reset 메서드](../Topic/event::reset%20Method.md)|이벤트를 신호되지 않은 상태로 다시 설정합니다.|  
|[event::set 메서드](../Topic/event::set%20Method.md)|이벤트를 발생시킵니다.|  
|[event::wait 메서드](../Topic/event::wait%20Method.md)|이벤트에서 신호를 보내게 될 때까지 기다립니다.|  
|[event::wait\_for\_multiple 메서드](../Topic/event::wait_for_multiple%20Method.md)|여러 이벤트에서 신호를 보내게 될 때까지 기다립니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[event::timeout\_infinite 상수](../Topic/event::timeout_infinite%20Constant.md)|대기가 시간 초과되지 않아야 함을 나타내는 값입니다.|  
  
## 설명  
 자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)을 참조하십시오.  
  
## 상속 계층  
 `event`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)