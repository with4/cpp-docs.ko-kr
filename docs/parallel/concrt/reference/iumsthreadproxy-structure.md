---
title: "IUMSThreadProxy 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSThreadProxy 구조체"
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSThreadProxy 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행 스레드에 대한 추상입니다.  스케줄러가 UMS\(User\-Mode Schedulable\) 스레드를 부여하려는 경우 스케줄러 정책 요소 `SchedulerKind`에 대한 값을 `UmsThreadDefault`로 설정하고 `IUMSScheduler` 인터페이스를 구현합니다.  UMS 스레드는 Windows 7 이상의 64비트 운영 체제에서만 지원됩니다.  
  
## 구문  
  
```  
struct IUMSThreadProxy : public IThreadProxy;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IUMSThreadProxy::EnterCriticalRegion 메서드](../Topic/IUMSThreadProxy::EnterCriticalRegion%20Method.md)|중요한 영역에 들어오기 위해 호출됩니다.  중요 영역 내에 있을 때 스케줄러는 영역에 있는 동안 발생하는 비동기 차단 작업을 관찰하지 않습니다.  이는 스케줄러가 UMS 스레드에 대한 페이지 폴트, 스레드 보류, 커널 비동기 APC\(비동기 프로시저 호출\) 등에 재진입되지 않음을 의미합니다.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion 메서드](../Topic/IUMSThreadProxy::EnterHyperCriticalRegion%20Method.md)|매우 중요한 영역에 들어오기 위해 호출됩니다.  매우 중요한 영역 내에 있을 때 스케줄러는 영역에 있는 동안 발생하는 모든 차단 작업을 관찰하지 않습니다.  이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단하는 잠금 획득 시도, 페이지 폴트, 스레드 보류, 커널 비동기 APC\(비동기 프로시저 호출\) 등에 재진입되지 않음을 의미합니다.|  
|[IUMSThreadProxy::ExitCriticalRegion 메서드](../Topic/IUMSThreadProxy::ExitCriticalRegion%20Method.md)|중요한 영역에서 나가기 위해 호출됩니다.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion 메서드](../Topic/IUMSThreadProxy::ExitHyperCriticalRegion%20Method.md)|매우 중요한 영역에서 나가기 위해 호출됩니다.|  
|[IUMSThreadProxy::GetCriticalRegionType 메서드](../Topic/IUMSThreadProxy::GetCriticalRegionType%20Method.md)|스레드 프록시가 들어 있는 중요 영역의 종류를 반환합니다.  매우 중요한 영역이 중요 영역의 상위 집합이기 때문에 코드가 중요 영역에 입력된 다음 매우 중요한 영역에 입력되는 경우 `InsideHyperCriticalRegion`이 반환됩니다.|  
  
## 상속 계층  
 [IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 구조체](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [SchedulerType 열거형](../Topic/SchedulerType%20Enumeration.md)