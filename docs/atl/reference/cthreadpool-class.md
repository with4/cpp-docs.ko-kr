---
title: "CThreadPool Class | Microsoft Docs"
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
  - "ATL.CThreadPool"
  - "ATL::CThreadPool"
  - "CThreadPool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CThreadPool class"
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CThreadPool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 큐의 작업 항목을 처리 하는 작업자 스레드 풀을 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   class Worker,  
   class ThreadTraits = DefaultThreadTraits  
>  
class CThreadPool :  
   public IThreadPoolConfig  
```  
  
#### 매개 변수  
 *작업자*  
 맞는 클래스는  [작업자 전형](../../atl/reference/worker-archetype.md) 항목의 스레드 풀에 대기 중인 작업을 처리 하는 코드를 제공 합니다.  
  
 `ThreadTraits`  
 풀에서 스레드를 만드는 데 사용 되는 함수를 제공 하는 클래스입니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CThreadPool::CThreadPool](../Topic/CThreadPool::CThreadPool.md)|스레드 풀에 대 한 생성자입니다.|  
|[CThreadPool::~CThreadPool](../Topic/CThreadPool::~CThreadPool.md)|스레드 풀에 대 한 소멸자가 있습니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CThreadPool::AddRef](../Topic/CThreadPool::AddRef.md)|`IUnknown::AddRef`의 구현입니다.|  
|[CThreadPool::GetNumThreads](../Topic/CThreadPool::GetNumThreads.md)|스레드 풀에서 가져오도록이 메서드를 호출 합니다.|  
|[CThreadPool::GetQueueHandle](../Topic/CThreadPool::GetQueueHandle.md)|작업 항목을 큐에 사용 되는 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[CThreadPool::GetSize](../Topic/CThreadPool::GetSize.md)|스레드 풀에서 가져오도록이 메서드를 호출 합니다.|  
|[CThreadPool::GetTimeout](../Topic/CThreadPool::GetTimeout.md)|스레드 풀 스레드 종료 대기 하는 밀리초 단위의 최대 시간이이 메서드를 호출 합니다.|  
|[CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md)|스레드 풀을 초기화 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::QueryInterface](../Topic/CThreadPool::QueryInterface.md)|구현 하는  **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](../Topic/CThreadPool::QueueRequest.md)|스레드 풀에 의해 처리 될 작업 항목을 큐에이 메서드를 호출 합니다.|  
|[CThreadPool::Release](../Topic/CThreadPool::Release.md)|`IUnknown::Release`의 구현입니다.|  
|[CThreadPool::SetSize](../Topic/CThreadPool::SetSize.md)|풀에서 스레드 수를 설정 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::SetTimeout](../Topic/CThreadPool::SetTimeout.md)|스레드 풀 스레드 종료 대기 하는 밀리초 단위의 최대 시간을 설정 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::Shutdown](../Topic/CThreadPool::Shutdown.md)|스레드 풀을 아래로 종료 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 스레드 풀에서을 만들고 풀 초기화, 크기 조정 또는 종료할 때 파괴 합니다.  클래스 인스턴스의  *작업자* 스택의 각 작업자 스레드 풀에서을 만들 수 있습니다.  각 스레드는 수명 동안 적용 됩니다.  
  
 스레드를 만든 후 즉시  *작업자*::`Initialize` 해당 스레드에 연결 개체에서 호출 됩니다.  스레드를 소멸 하기 직전  *작업자*::`Terminate` 호출 됩니다.  두 메서드 모두 동의 해야는  **void \*** 인수.  이 인수의 값은 스레드 풀을 통해 전달 되는 `pvWorkerParam` 매개 변수를  [CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md).  
  
 항목 큐 및 호출 작업자 스레드를 끌어올 경우 작업 항목 큐와 작업자 스레드를 작업에 사용할 수 있는  **실행** 메서드는  *작업자* 해당 스레드에 대 한 개체.  세 항목 다음 메서드에 전달: 동일한 큐에서 항목 `pvWorkerParam` 전달  *작업자*::`Initialize` 및  *작업자*::`Terminate`를 가리키는 포인터는  [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) IO 완료 포트 큐에 사용 되는 구조.  
  
 *작업자* 클래스 형식 정의 제공 하 여 스레드 풀에 대기 합니다. 항목 형식을 선언  *작업자*::`RequestType`.  이 형식에서 하 고 캐스팅 되 고의 가능 해야는  **ULONG\_PTR**.  
  
 예로  *작업자* 클래스인 [CNonStatelessWorker Class](../../atl/reference/cnonstatelessworker-class.md).  
  
## 상속 계층 구조  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [IThreadPoolConfig Interface](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [클래스](../../atl/reference/atl-classes.md)