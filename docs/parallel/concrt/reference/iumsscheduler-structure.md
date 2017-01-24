---
title: "IUMSScheduler 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSScheduler 구조체"
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSScheduler 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임 리소스 관리자 사용자가 UMS\(User\-Mode Schedulable\) 스레드에 전달하려는 작업 스케줄러의 추상화에 대한 인터페이스입니다.  리소스 관리자는 이 인터페이스를 사용하여 UMS 스레드 스케줄러와 통신합니다.  `IUMSScheduler` 인터페이스는 `IScheduler` 인터페이스에서 상속합니다.  
  
## 구문  
  
```  
struct IUMSScheduler : public IScheduler;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IUMSScheduler::SetCompletionList 메서드](../Topic/IUMSScheduler::SetCompletionList%20Method.md)|`IUMSCompletionList` 인터페이스는 UMS 스레드 스케줄러에 할당합니다.|  
  
## 설명  
 리소스 관리자와 통신하는 사용자 지정 스케줄러를 구현하고 UMS 스레드를 일반 Win32 스레드 대신 스케줄러로 전달하려는 경우 `IUMSScheduler` 인터페이스의 구현을 제공해야 합니다.  또한, 스케줄러 정책 키 `SchedulerKind`가 `UmsThreadDefault`가 되도록 정책 값을 설정해야 합니다.  정책이 UMS 스레드를 지정하는 경우 [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) 메서드에 매개 변수로 전달되는 `IScheduler` 인터페이스는 `IUMSScheduler` 인터페이스가 되어야 합니다.  
  
 리소스 관리자는 UMS 스레드를 UMS 기능이 있는 운영 체제에만 전달할 수 있습니다. 64비트 운영 체제 버전 Windows 7 이상이 UMS 스레드를 지원합니다.  `SchedulerKind` 키를 값 `UmsThreadDefault`로 설정한 상태에서 스케줄러 정책을 만들고 기본 플랫폼이 UMS를 지원하지 않을 경우 해당 정책에서 `SchedulerKind` 키의 값은 값 `ThreadScheduler`로 변경됩니다.  항상 UMS 스레드 받기 전에 이 정책 값을 다시 읽어야 합니다.  
  
 `IUMSScheduler` 인터페이스는 스케줄러와 리소스 관리자 사이의 양방향 통신 채널 중 한 쪽 끝입니다.  다른 쪽 끝은 리소스 관리자에 의해 구현되는 `IResourceManager` 및 `ISchedulerProxy` 인터페이스로 표현됩니다.  
  
## 상속 계층  
 [IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [IScheduler 구조체](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IUMSCompletionList 구조체](../../../parallel/concrt/reference/iumscompletionlist-structure.md)   
 [IResourceManager 구조체](../../../parallel/concrt/reference/iresourcemanager-structure.md)