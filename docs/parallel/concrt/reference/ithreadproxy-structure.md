---
title: "IThreadProxy 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::IThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadProxy 구조체"
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IThreadProxy 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행 스레드에 대한 추상입니다.  사용자가 만드는 `SchedulerType` 정책 키에 따라 리소스 관리자는 일반 Win32 스레드 또는 UMS\(User\-Mode Schedulable\) 스레드가 지원하는 스레드 프록시를 제공합니다.  UMS 스레드는 Windows 7 이상의 64비트 운영 체제에서 지원됩니다.  
  
## 구문  
  
```  
struct IThreadProxy;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IThreadProxy::GetId 메서드](../Topic/IThreadProxy::GetId%20Method.md)|스레드 프록시에 대한 고유 식별자를 반환합니다.|  
|[IThreadProxy::SwitchOut 메서드](../Topic/IThreadProxy::SwitchOut%20Method.md)|컨텍스트를 내부 가상 프로세서 루트에서 연결을 끊습니다.|  
|[IThreadProxy::SwitchTo 메서드](../Topic/IThreadProxy::SwitchTo%20Method.md)|현재 실행 중인 컨텍스트에서 다른 컨텍스트로 협력 컨텍스트 전환을 수행합니다.|  
|[IThreadProxy::YieldToSystem 메서드](../Topic/IThreadProxy::YieldToSystem%20Method.md)|호출 스레드가 현재 프로세서에서 실행할 준비가 되어 있는 다른 스레드에 실행 명령을 내리도록 합니다.  운영 체제에서 실행될 다음 스레드를 선택합니다.|  
  
## 설명  
 스레드 프록시는 디스패치 작업의 수단으로 인터페이스 `IExecutionContext`에 의해 표현되는 실행 컨텍스트에 결합됩니다.  
  
## 상속 계층  
 `IThreadProxy`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext 구조체](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IScheduler 구조체](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IVirtualProcessorRoot 구조체](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)