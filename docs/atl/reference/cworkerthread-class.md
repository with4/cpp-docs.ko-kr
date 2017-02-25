---
title: "CWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWorkerThread<ThreadTraits>"
  - "ATL::CWorkerThread"
  - "ATL.CWorkerThread"
  - "ATL.CWorkerThread<ThreadTraits>"
  - "CWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWorkerThread class"
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 작업자 스레드를 만듭니다 또는 기존 사용, 여러 커널 개체 핸들을 대기 및 신호를 핸들 중 하나를 지정한 클라이언트 함수 실행.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class ThreadTraits= DefaultThreadTraits  
>  
class CWorkerThread  
```  
  
#### 매개 변수  
 `ThreadTraits`  
 같은 스레드 생성 함수를 제공 하는 클래스  [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) 또는  [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## Members  
  
### 보호 구조  
  
|Name|설명|  
|----------|--------|  
|`WorkerClientEntry`||  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWorkerThread::CWorkerThread](../Topic/CWorkerThread::CWorkerThread.md)|작업자 스레드에 대 한 생성자입니다.|  
|[CWorkerThread::~CWorkerThread](../Topic/CWorkerThread::~CWorkerThread.md)|작업자 스레드에 대 한 소멸자가 있습니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md)|대기 가능 개체의 핸들을 작업자 스레드에 의해 유지 목록에 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md)|대기 가능 타이머를 주기적으로 작업자 스레드에 의해 유지 목록에 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md)|작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md)|작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md)|작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md)|대기 가능 개체 목록에서 핸들을 제거 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md)|작업자 스레드를 종료 하려면이 메서드를 호출 합니다.|  
  
## 설명  
  
### Cworkerthread를 사용.  
  
1.  이 클래스의 인스턴스를 만듭니다.  
  
2.  호출  [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).  
  
3.  호출  [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md) 의 구현에 대 한 포인터와 커널 개체 핸들을 사용  [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     – 또는 –  
  
     호출  [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md) 의 구현에 대 한 포인터가  [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  구현  [IWorkerThreadClient::Execute](../Topic/IWorkerThreadClient::Execute.md) 신호를 핸들 또는 타이머 일부 작업을 수행할 수 있습니다.  
  
5.  호출 대기 가능 개체 목록에서 개체를 제거 하려면  [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).  
  
6.  호출 스레드가 종료 하려면  [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [클래스](../../atl/reference/atl-classes.md)   
 [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient Interface](../../atl/reference/iworkerthreadclient-interface.md)