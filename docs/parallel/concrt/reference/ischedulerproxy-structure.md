---
title: "ISchedulerProxy 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs: C++
helpviewer_keywords: ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b151e68c9cce0113c46f0eaffff8e19ed4d5c896
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 구조체
스케줄러가 리소스 할당을 협상하기 위해 동시성 런타임의 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Ischedulerproxy:: Bindcontext](#bindcontext)|아직 하 나와 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.|  
|[Ischedulerproxy:: Createoversubscriber](#createoversubscriber)|기존 실행 리소스와 연결 된 하드웨어 스레드에 새로운 가상 프로세서 루트를 만듭니다.|  
|[Ischedulerproxy:: Requestinitialvirtualprocessors](#requestinitialvirtualprocessors)|가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.|  
|[Ischedulerproxy:: Shutdown](#shutdown)|스케줄러가 종료 되 고 리소스 관리자에 알립니다. 이렇게 하면 리소스 관리자에서 스케줄러에 허용 되는 모든 리소스를 즉시 회수 하 합니다.|  
|[Ischedulerproxy:: Subscribecurrentthread](#subscribecurrentthread)|현재 스레드가 리소스 관리자와이 스케줄러와 연결을 등록 합니다.|  
|[Ischedulerproxy:: Unbindcontext](#unbindcontext)|로 지정 된 실행 컨텍스트를 스레드 프록시 연결을 해제는 `pContext` 매개 변수 스레드 프록시 팩터리의 사용 가능한 풀으로 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된에 호출할 수는 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 고 통해 아직 시작 되지 않은 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto ](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 리소스 관리자에 전달 된 `ISchedulerProxy` 를 사용 하 여 등록 하는 모든 스케줄러에 대 한 인터페이스는 [iresourcemanager:: Registerscheduler](iresourcemanager-structure.md#registerscheduler) 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="bindcontext"></a>Ischedulerproxy:: Bindcontext 메서드  
 아직 하 나와 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 스레드 프록시를 통해 연결할 실행 컨텍스트를 사용 하는 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 [ithreadproxy:: Switchto](ithreadproxy-structure.md#switchto) 메서드는 요청 시 실행 컨텍스트를 스레드 프록시를 바인딩합니다. 그러나는, 사전에 있는지 확인 하는 컨텍스트가 바인딩할 필요가 한 상황에서 `SwitchTo` 메서드는 이미 바인딩된 컨텍스트를 전환 합니다. 이 메모리를 할당 하는 메서드를 호출할 수 없습니다 일정 컨텍스트에서 ums 경우 하며 스레드 프록시를 바인딩 수 이루어집니다 메모리 할당 스레드 프록시 팩터리의 사용 가능한 풀에 스레드 프록시를 손쉽게 사용할 수 없는 경우.  
  
 `invalid_argument`경우 throw 되는 매개 변수 `pContext` 값 `NULL`합니다.  
  
##  <a name="createoversubscriber"></a>Ischedulerproxy:: Createoversubscriber 메서드  
 기존 실행 리소스와 연결 된 하드웨어 스레드에 새로운 가상 프로세서 루트를 만듭니다.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pExecutionResource`  
 `IExecutionResource` 초과 구독 하려는 하드웨어 스레드를 나타내는 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 `IVirtualProcessorRoot` 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 스케줄러 제한 된 기간에 대 한 특정 하드웨어 스레드를 초과 구독 하려고 할 때이 메서드를 사용 합니다. 가상 프로세서 루트와 함께 완료 반환 해야 리소스 관리자에 게 호출 하 여는 [제거](iexecutionresource-structure.md#remove) 에서 메서드는 `IVirtualProcessorRoot` 인터페이스입니다.  
  
 `IVirtualProcessorRoot` 인터페이스가 `IExecutionResource` 인터페이스에서 상속하기 때문에 기존 가상 프로세서 루트를 초과 구독할 수도 있습니다.  
  
##  <a name="requestinitialvirtualprocessors"></a>Ischedulerproxy:: Requestinitialvirtualprocessors 메서드  
 가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `doSubscribeCurrentThread`  
 현재 스레드를 구독 하 고 리소스 할당 하는 동안 고려 여부를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 `IExecutionResource` 현재 스레드에 대 한 인터페이스 매개 변수 `doSubscribeCurrentThread` 값 `true`합니다. 값이 `false`, 메서드가 반환 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 스케줄러는 모든 작업을 실행 하기 전에 리소스 관리자에서 가상 프로세서 루트를 요청 하려면이 메서드를 사용 해야 합니다. 스케줄러의 정책에 액세스 하는 리소스 관리자를 사용 하 여 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 정책 키에 대 한 값을 사용 하 고 `MinConcurrency`, `MaxConcurrency` 및 `TargetOversubscriptionFactor` 에 할당할 하드웨어 스레드 수를 결정 하는 스케줄러 처음 하 고 모든 하드웨어 스레드에 대해 만들려는 가상 프로세서 루트 수 있습니다. 스케줄러의 처음 할당을 확인 하려면 스케줄러 정책을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [PolicyElementKey](concurrency-namespace-enums.md)합니다.  
  
 리소스 관리자는 메서드를 호출 하 여 스케줄러에 리소스를 부여 [ischeduler:: Addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors) 가상 프로세서 루트의 목록을 사용 합니다. 메서드는이 메서드가 반환 되기 전에 스케줄러에 대 한 콜백 호출 됩니다.  
  
 스케줄러 매개 변수를 설정 하 여 현재 스레드에 대 한 구독을 요청 하는 경우 `doSubscribeCurrentThread` 를 `true`, 메서드는 `IExecutionResource` 인터페이스입니다. 구독을 나중에 사용 하 여 종료 해야 합니다는 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드.  
  
 하드웨어 스레드 선택을 결정할 때 리소스 관리자 프로세서 노드 선호도 대 한 최적화 하려고 합니다. 현재 스레드에 대 한 구독이 요청 되는 현재 스레드에서이 스케줄러에 할당 된 작업에 참여 하도록 하려는 나타냅니다. 이 경우 할당 된 가상 프로세서 루트는 현재 스레드가 실행 되 고, 가능 하면 프로세서 로드에 있습니다.  
  
 스레드의 구독에 대 한 수준의 기본 하드웨어 스레드 하나 증가 합니다. 구독이 종료 되 면 구독 수준은 1 씩 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="shutdown"></a>Ischedulerproxy:: Shutdown 메서드  
 스케줄러가 종료 되 고 리소스 관리자에 알립니다. 이렇게 하면 리소스 관리자에서 스케줄러에 허용 되는 모든 리소스를 즉시 회수 하 합니다.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>설명  
 모든 `IExecutionContext` 인터페이스 메서드를 사용 하는 외부 스레드가 구독 결과로 받은 스케줄러 `ISchedulerProxy::RequestInitialVirtualProcessors` 또는 `ISchedulerProxy::SubscribeCurrentThread` 리소스 관리자에 반환 되어야 합니다를 사용 하 여 `IExecutionResource::Remove` 는 스케줄러가 종료 전에 합니다.  
  
 가상 프로세서 루트를 비활성화 하는 모든 스케줄러에 있으면, 활성화 해야 합니다를 사용 하 여 [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate), 스레드 프록시를 실행 상태로 유지 되었으며는 `Dispatch` 실행 메서드 호출 전에 디스패치 하는 이러한 컨텍스트 `Shutdown` 스케줄러 프록시에 있습니다.  
  
 모든 가상 프로세서 루트는 종료 시 리소스 관리자로 반환되기 때문에 리소스 관리자가 `Remove` 메서드 호출을 통해 부여한 모든 가상 프로세서 루트를 스케줄러가 개별적으로 반환할 필요는 없습니다.  
  
##  <a name="subscribecurrentthread"></a>Ischedulerproxy:: Subscribecurrentthread 메서드  
 현재 스레드가 리소스 관리자와이 스케줄러와 연결을 등록 합니다.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IExecutionResource` 런타임에서 현재 스레드를 나타내는 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자에서 스케줄러 및 다른 스케줄러에 리소스를 할당 하는 동안 현재 스레드를 고려 하는 경우이 방법을 사용 합니다. 스케줄러 수신 되었다는 리소스 관리자의 가상 프로세서 루트와 함께 사용자의 스케줄러에 작업에 참여 하도록 하는 스레드 계획 대기 하는 경우에 특히 유용 합니다. 리소스 관리자 시스템 하드웨어 스레드 불필요 한 초과 구독을 방지 하기 위해 정보를 사용 합니다.  
  
 이 메서드를 통해 받은 실행 리소스를 반환할 리소스 관리자를 사용 하 여는 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드. 호출 하는 스레드에서 `Remove` 메서드 이전에 호출 하는 이어야 합니다는 `SubscribeCurrentThread` 메서드.  
  
 스레드의 구독에 대 한 수준의 기본 하드웨어 스레드 하나 증가 합니다. 구독이 종료 되 면 구독 수준은 1 씩 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="unbindcontext"></a>Ischedulerproxy:: Unbindcontext 메서드  
 로 지정 된 실행 컨텍스트를 스레드 프록시 연결을 해제는 `pContext` 매개 변수 스레드 프록시 팩터리의 사용 가능한 풀으로 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된에 호출할 수는 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 고 통해 아직 시작 되지 않은 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto ](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 해당 스레드 프록시로의 연결을 끊을 실행 컨텍스트.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IScheduler 구조체](ischeduler-structure.md)   
 [IThreadProxy 구조체](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)   
 [IResourceManager 구조체](iresourcemanager-structure.md)
