---
title: "task_completion_event 클래스 | Microsoft Docs"
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
  - "ppltasks/concurrency::task_completion_event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_completion_event 클래스"
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_completion_event 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_completion_event` 클래스를 사용하면 조건을 충족할 때까지 작업 실행을 미루거나 외부 이벤트에 대한 응답으로 작업을 시작할 수 있습니다.  
  
## 구문  
  
```  
template<  
   typename _ResultType  
>  
class task_completion_event;  
  
template<>  
class task_completion_event<void>;  
```  
  
#### 매개 변수  
 `_ResultType`  
 이 `task_completion_event` 클래스의 결과 형식입니다.  
  
 `T`  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[task\_completion\_event::task\_completion\_event 생성자](../Topic/task_completion_event::task_completion_event%20Constructor.md)|`task_completion_event` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[task\_completion\_event::set 메서드](../Topic/task_completion_event::set%20Method.md)|오버로드됨.  작업 완료 이벤트를 설정합니다.|  
|[task\_completion\_event::set\_exception 메서드](../Topic/task_completion_event::set_exception%20Method.md)|오버로드됨.  이 이벤트와 관련된 모든 작업에 예외를 전파합니다.|  
  
## 설명  
 시나리오에서 완료할 작업을 만들도록 요청할 경우 작업 완료 이벤트에서 만든 작업을 사용하고 나중에 특정 시점에서 연속 작업이 실행되도록 예약합니다.  `task_completion_event`에는 만든 작업과 동일한 형식이 있어야 하며, 작업 완료 이벤트에서 해당 형식의 값으로 set 메서드를 호출하면 관련 작업이 완료되고 해당 값을 해당 연속 작업의 결과로 제공합니다.  
  
 작업 완료 이벤트가 신호를 받지 못하는 경우 이벤트에서 생성된 모든 작업은 소멸되는 시점에서 취소됩니다.  
  
 `task_completion_event`는 스마트 포인터처럼 동작하고 값에 의해 전달되어야 합니다.  
  
## 상속 계층  
 `task_completion_event`  
  
## 요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ko-kr/5389e8a5-5038-40b6-844a-55e9b58ad35f)