---
title: "DispatchState 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::DispatchState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DispatchState 구조체"
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DispatchState 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`DispatchState` 구조는 `IExecutionContext::Dispatch` 메서드에 상태를 전송하는 데 사용됩니다.  `Dispatch` 메서드가 `IExecutionContext` 인스턴스에서 호출되는 상황을 설명합니다.  
  
## 구문  
  
```  
struct DispatchState;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[DispatchState::DispatchState 생성자](../Topic/DispatchState::DispatchState%20Constructor.md)|새 `DispatchState` 개체를 생성합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[DispatchState::m\_dispatchStateSize 데이터 멤버](../Topic/DispatchState::m_dispatchStateSize%20Data%20Member.md)|버전 관리에 사용되는 이 구조의 크기입니다.|  
|[DispatchState::m\_fIsPreviousContextAsynchronouslyBlocked 데이터 멤버](../Topic/DispatchState::m_fIsPreviousContextAsynchronouslyBlocked%20Data%20Member.md)|이전 컨텍스트가 비동기적으로 차단되었기 때문에 이 컨텍스트가 `Dispatch` 메서드를 입력했는지 여부를 알립니다.  이는 UMS 일정 컨텍스트에서만 사용되며 다른 모든 실행 컨텍스트에 대해 값 `0`으로 설정됩니다.|  
|[DispatchState::m\_reserved 데이터 멤버](../Topic/DispatchState::m_reserved%20Data%20Member.md)|향후 정보 전달을 위해 예약된 비트입니다.|  
  
## 상속 계층  
 `DispatchState`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext::Dispatch 메서드](../Topic/IExecutionContext::Dispatch%20Method.md)