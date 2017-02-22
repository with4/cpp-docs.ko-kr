---
title: "IResourceManager 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IResourceManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IResourceManager 구조체"
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# IResourceManager 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임 리소스 관리자에 대한 인터페이스입니다.  스케줄러가 리소스 관리자를 사용하여 통신하는 인터페이스입니다.  
  
## 구문  
  
```  
struct IResourceManager;  
```  
  
## 멤버  
  
### Public 열거형  
  
|Name|설명|  
|----------|--------|  
|[IResourceManager::OSVersion 열거형](../Topic/IResourceManager::OSVersion%20Enumeration.md)|운영 체제 버전을 나타내는 열거 형식입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IResourceManager::CreateNodeTopology 메서드](../Topic/IResourceManager::CreateNodeTopology%20Method.md)|런타임의 디버그 빌드에서만 제공되는 이 메서드는 구성과 일치하는 실제 하드웨어를 요구하지 않고 다양한 하드웨어 토폴로지에서 리소스 관리자의 테스트를 이용하도록 설계된 테스트 후크입니다.  런타임의 정식 버전 빌드를 사용하면 이 메서드는 아무 작업도 수행하지 않고 반환합니다.|  
|[IResourceManager::GetAvailableNodeCount 메서드](../Topic/IResourceManager::GetAvailableNodeCount%20Method.md)|리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.|  
|[IResourceManager::GetFirstNode 메서드](../Topic/IResourceManager::GetFirstNode%20Method.md)|리소스 관리자가 정의한 열거 순서에서 첫 번째 노드를 반환합니다.|  
|[IResourceManager::Reference 메서드](../Topic/IResourceManager::Reference%20Method.md)|리소스 관리자 인스턴스에서 참조 횟수를 증가시킵니다.|  
|[IResourceManager::RegisterScheduler 메서드](../Topic/IResourceManager::RegisterScheduler%20Method.md)|리소스 관리자를 사용하여 스케줄러를 등록합니다.  스케줄러가 등록된 후에는 반환되는 `ISchedulerProxy` 인터페이스를 사용하여 리소스 관리자와 통신해야 합니다.|  
|[IResourceManager::Release 메서드](../Topic/IResourceManager::Release%20Method.md)|리소스 관리자 인스턴스에서 참조 횟수를 감소시킵니다.  참조 횟수가 `0`이 될 때 리소스 관리자는 소멸됩니다.|  
  
## 설명  
 [CreateResourceManager](../Topic/CreateResourceManager%20Function.md) 함수를 사용하여 단일 리소스 관리자 인스턴스에 대한 인터페이스를 가져옵니다.  메서드는 리소스 관리자에서 참조 횟수를 증가시키고 리소스 관리자와의 작업을 완료했을 때 참조를 해제하도록 [IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md) 메서드를 호출해야 합니다.  일반적으로 사용자가 만드는 각 스케줄러는 만드는 동안 이 메서드를 호출하고 종료된 후에 리소스 관리자에 대한 참조를 해제합니다.  
  
## 상속 계층  
 `IResourceManager`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISchedulerProxy 구조체](../../../parallel/concrt/reference/ischedulerproxy-structure.md)   
 [IScheduler 구조체](../../../parallel/concrt/reference/ischeduler-structure.md)