---
title: "IUMSUnblockNotification 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSUnblockNotification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSUnblockNotification 구조체"
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSUnblockNotification 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

차단되고 트리거된 스레드 프록시가 스케줄러의 지정된 일정 컨텍스트를 반환하는 리소스 관리자의 알림이 차단되었으며 예약 준비가 되었음을 나타냅니다.  이 인터페이스는 `GetContext` 메서드에서 반환되는 스레드 프록시의 관련 실행 컨텍스트를 다시 예약하면 잘못됩니다.  
  
## 구문  
  
```  
struct IUMSUnblockNotification;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IUMSUnblockNotification::GetContext 메서드](../Topic/IUMSUnblockNotification::GetContext%20Method.md)|차단 해제된 스레드 프록시에 연결된 실행 컨텍스트의 `IExecutionContext` 인터페이스를 반환합니다.  이 메서드를 반환하고 기본 실행 컨텍스트가 `IThreadProxy::SwitchTo` 메서드에 대한 호출을 통해 다시 예약되면 이 인터페이스는 더 이상 유효하지 않습니다.|  
|[IUMSUnblockNotification::GetNextUnblockNotification 메서드](../Topic/IUMSUnblockNotification::GetNextUnblockNotification%20Method.md)|메서드 `IUMSCompletionList::GetUnblockNotifications`에서 반환된 체인에 있는 다음 `IUMSUnblockNotification` 인터페이스를 반환합니다.|  
  
## 상속 계층  
 `IUMSUnblockNotification`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 구조체](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSCompletionList 구조체](../../../parallel/concrt/reference/iumscompletionlist-structure.md)