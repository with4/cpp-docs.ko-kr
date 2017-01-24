---
title: "CNonStatelessWorker Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CNonStatelessWorker<Worker>"
  - "ATL::CNonStatelessWorker"
  - "ATL.CNonStatelessWorker"
  - "CNonStatelessWorker"
  - "ATL::CNonStatelessWorker<Worker>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNonStatelessWorker class"
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNonStatelessWorker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드 풀에서 요청을 받아이 만들어지고 소멸 하는 작업자 개체에 각 요청을 전달 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class Worker  
>  
class CNonStatelessWorker  
```  
  
#### 매개 변수  
 *작업자*  
 맞는 작업자 스레드 클래스는  [작업자 전형](../../atl/reference/worker-archetype.md) 큐에 처리 요청에 대해 적합 한  [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CNonStatelessWorker::RequestType](../Topic/CNonStatelessWorker::RequestType.md)|구현 하는  [WorkerArchetype::RequestType](../Topic/WorkerArchetype::RequestType.md).|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CNonStatelessWorker::Execute](../Topic/CNonStatelessWorker::Execute.md)|구현 하는  [WorkerArchetype::Execute](../Topic/WorkerArchetype::Execute.md).|  
|[CNonStatelessWorker::Initialize](../Topic/CNonStatelessWorker::Initialize.md)|구현 하는  [WorkerArchetype::Initialize](../Topic/WorkerArchetype::Initialize.md).|  
|[CNonStatelessWorker::Terminate](../Topic/CNonStatelessWorker::Terminate.md)|구현 하는  [WorkerArchetype::Terminate](../Topic/WorkerArchetype::Terminate.md).|  
  
## 설명  
 이 클래스 사용에 대 한 간단한 작업자 스레드입니다  [CThreadPool](../../atl/reference/cthreadpool-class.md).  이 클래스는 자체의 요청 처리 기능을 제공 하지 않습니다.  대신 인스턴스를 인스턴스화하고  *작업자* 요청 당 및 대리자의 해당 인스턴스에 메서드를 구현 합니다.  
  
 이 클래스는 기존 작업자 스레드 클래스에 대 한 상태 모델을 변경 하는 편리한 방법을 제공 하는 유용 합니다.  `CThreadPool`단일 작업자 스레드를 하는 동안 만들어집니다 작업자 클래스 상태를 유지 하는 경우는 여러 요청에 저장 될 수 있습니다.  해당 클래스에 간단 하 게 배치 하는 `CNonStatelessWorker` 서식 파일을 사용 하기 전에 `CThreadPool`, 단일 요청으로 제한 되어 있는 상태는 작업자의 수명.  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)   
 [Worker Archetype](../../atl/reference/worker-archetype.md)   
 [클래스](../../atl/reference/atl-classes.md)