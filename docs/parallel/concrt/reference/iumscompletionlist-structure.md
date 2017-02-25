---
title: "IUMSCompletionList 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSCompletionList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSCompletionList 구조체"
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSCompletionList 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

UMS 완성 목록을 나타냅니다.  UMS 스레드가 차단되면 원래 스레드가 차단된 동안 기본 가상 프로세서에 무엇을 예약할지 결정하기 위해 스케줄러의 지정된 일정 컨텍스트가 디스패치됩니다.  원래 스레드 차단이 해제되면 운영 체제는 이 인터페이스를 통해 액세스할 수 있는 완성 목록의 큐에 추가합니다.  스케줄러는 지정된 일정 컨텍스트에 대한 완성 목록이나 작업을 검색할 다른 위치를 쿼리할 수 있습니다.  
  
## 구문  
  
```  
struct IUMSCompletionList;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IUMSCompletionList::GetUnblockNotifications 메서드](../Topic/IUMSCompletionList::GetUnblockNotifications%20Method.md)|관련된 스레드 프록시가 이 메서드가 호출된 이후로 차단이 해제된 실행 컨텍스트를 나타내는 `IUMSUnblockNotification` 인터페이스의 체인을 검색합니다.|  
  
## 설명  
 스케줄러는 완성 목록에서 항목을 큐에서 제거하기 위해 이 인터페이스를 이용한 후에 어떤 작업을 수행할지에 대해 주의해야 합니다.  항목은 실행 가능한 컨텍스트의 스케줄러 목록에 저장되며 일반적으로 가능한 빨리 액세스할 수 있습니다.  큐에서 제거된 항목 중 하나에 임의 잠금의 소유권이 부여되었을 가능성이 높습니다.  스케줄러는 항목을 큐에서 제거하기 위한 호출과 이러한 항목을 스케줄러 내에서 일반적으로 액세스할 수 있는 목록에 배치하는 사이에 차단할 수 있는 임의의 함수 호출을 할 수 없습니다.  
  
## 상속 계층  
 `IUMSCompletionList`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 구조체](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSUnblockNotification 구조체](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)