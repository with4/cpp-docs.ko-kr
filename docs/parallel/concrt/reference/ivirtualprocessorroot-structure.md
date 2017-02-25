---
title: "IVirtualProcessorRoot 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IVirtualProcessorRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IVirtualProcessorRoot 구조체"
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IVirtualProcessorRoot 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

스레드 프록시를 실행할 수 있는 하드웨어 스레드에 대한 추상화.  
  
## 구문  
  
```  
struct IVirtualProcessorRoot : public IExecutionResource;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IVirtualProcessorRoot::Activate 메서드](../Topic/IVirtualProcessorRoot::Activate%20Method.md)|이 가상 프로세서 루트에서 실행 컨텍스트 인터페이스 `pContext`와 연결된 스레드 프록시가 실행을 시작하게 됩니다.|  
|[IVirtualProcessorRoot::Deactivate 메서드](../Topic/IVirtualProcessorRoot::Deactivate%20Method.md)|이 가상 프로세서 루트에서 현재 실행 중인 스레드 프록시가 실행 컨텍스트 디스패치를 중지하게 됩니다.  스레드 프록시는 `Activate` 메서드에 대한 호출 실행을 다시 시작합니다.|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible 메서드](../Topic/IVirtualProcessorRoot::EnsureAllTasksVisible%20Method.md)|시스템에 있는 모든 프로세서가 볼 수 있도록 개별 프로세서의 메모리 계층에 데이터가 저장됩니다.  메서드를 반환하기 전에 모든 처리기에서 전체 메모리 펜스가 실행되도록 합니다.|  
|[IVirtualProcessorRoot::GetId 메서드](../Topic/IVirtualProcessorRoot::GetId%20Method.md)|가상 프로세서 루트에 대한 고유 식별자를 반환합니다.|  
  
## 설명  
 모든 가상 프로세서 루트에는 연결된 실행 리소스가 있습니다.  `IVirtualProcessorRoot` 인스턴스는 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md) 인터페이스에서 상속됩니다.  여러 가상 프로세서 루트는 동일한 기본 하드웨어 스레드에 해당할 수 있습니다.  
  
 리소스 관리자는 리소스에 대한 요청에 대한 응답으로 스케줄러에 가상 프로세서 루트를 부여합니다.  스케줄러는 가상 프로세서 루트를 사용하여 실행 컨텍스트를 활성화하여 작업을 수행할 수 있습니다.  
  
## 상속 계층  
 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)