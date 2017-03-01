---
title: "ISchedulerProxy 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ISchedulerProxy
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: a282e397186ee4ab3eda4f882b9c9fc89ff353f2
ms.lasthandoff: 02/24/2017

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
|[Ischedulerproxy:: Bindcontext 메서드](#bindcontext)|아직 하 나와 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.|  
|[Ischedulerproxy:: Createoversubscriber 메서드](#createoversubscriber)|기존 실행 리소스와 관련 된 하드웨어 스레드에 새로운 가상 프로세서 루트를 만듭니다.|  
|[Ischedulerproxy:: Requestinitialvirtualprocessors 메서드](#requestinitialvirtualprocessors)|가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.|  
|[Ischedulerproxy:: Shutdown 메서드](#shutdown)|스케줄러가 종료 되는 리소스 관리자에 알립니다. 이렇게 하면 리소스 관리자에서 스케줄러에 부여 된 모든 리소스를 즉시 회수를 합니다.|  
|[Ischedulerproxy:: Subscribecurrentthread 메서드](#subscribecurrentthread)|현재 스레드의 리소스 관리자를이 스케줄러와 연결을 등록 합니다.|  
|[Ischedulerproxy:: Unbindcontext 메서드](#unbindcontext)|지정한 실행 컨텍스트에서 스레드 프록시 연결을 해제는 `pContext` 매개 변수 스레드 프록시 팩터리의 사용 가능한 풀으로 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된에 호출할 수 있습니다는 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 고를 통해 아직 시작 되지 않은 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 전달 하는 리소스 관리자는 `ISchedulerProxy` 인터페이스를 사용 하 여 등록 하는 모든 스케줄러에는 [iresourcemanager:: Registerscheduler](iresourcemanager-structure.md#registerscheduler) 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namebindcontexta--ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>Ischedulerproxy:: Bindcontext 메서드  
 아직 하 나와 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 스레드 프록시를 연결할 실행 컨텍스트는 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 [ithreadproxy:: Switchto](ithreadproxy-structure.md#switchto) 메서드는 필요에 따라 실행 컨텍스트를 스레드 프록시를 바인딩합니다. 그러나는, 미리 되도록 컨텍스트를 바인딩하여 하는 데 필요한 경우는 `SwitchTo` 메서드는 이미 바인딩된 컨텍스트를 전환 합니다. 이 경우에 메모리를 할당 하는 메서드를 호출할 수 없습니다 일정 컨텍스트에서 ums 및 스레드 프록시를 바인딩 눌러야 메모리 할당 스레드 프록시 팩터리의 사용 가능한 풀에서 스레드 프록시를 즉시 사용할 수 없는 경우.  
  
 `invalid_argument`경우 throw 되는 매개 변수 `pContext` 값 `NULL`합니다.  
  
##  <a name="a-namecreateoversubscribera--ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>Ischedulerproxy:: Createoversubscriber 메서드  
 기존 실행 리소스와 관련 된 하드웨어 스레드에 새로운 가상 프로세서 루트를 만듭니다.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pExecutionResource`  
 `IExecutionResource` 초과 구독 하려는 하드웨어 스레드를 나타내는 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 `IVirtualProcessorRoot` 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 스케줄러 제한 된 기간에 대 한 특정 하드웨어 스레드의 초과 구독 하려는 경우이 메서드를 사용 합니다. 가상 프로세서 루트를 완료 해야이 리소스 관리자에 게 호출 하 여 반환 된 [제거](iexecutionresource-structure.md#remove) 메서드를는 `IVirtualProcessorRoot` 인터페이스입니다.  
  
 `IVirtualProcessorRoot` 인터페이스가 `IExecutionResource` 인터페이스에서 상속하기 때문에 기존 가상 프로세서 루트를 초과 구독할 수도 있습니다.  
  
##  <a name="a-namerequestinitialvirtualprocessorsa--ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>Ischedulerproxy:: Requestinitialvirtualprocessors 메서드  
 가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `doSubscribeCurrentThread`  
 현재 스레드를 구독 하 고 리소스 할당 중에 대 한 계정 여부를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 `IExecutionResource` 경우 현재 스레드에 대 한 인터페이스 매개 변수 `doSubscribeCurrentThread` 값 `true`합니다. 값이 `false`, 메서드가 반환 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 스케줄러는 모든 작업을 실행 하기 전에 리소스 관리자에서 가상 프로세서 루트를 요청 하려면이 메서드를 사용 해야 합니다. 리소스 관리자는 스케줄러 정책의 액세스를 사용 하 여 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 정책 키에 대 한 값을 사용 하 고 `MinConcurrency`, `MaxConcurrency` 및 `TargetOversubscriptionFactor` 처음 스케줄러에 할당할 하드웨어 스레드 수를 결정 하는 모든 하드웨어 스레드를 만드는 얼마나 많은 가상 프로세서 루트를 합니다. 스케줄러의 초기 할당 결정를 스케줄러 정책을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [PolicyElementKey](concurrency-namespace-enums.md)합니다.  
  
 리소스 관리자를 사용 하는 메서드를 호출 하 여 스케줄러에 리소스를 부여 [ischeduler:: Addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors) 가상 프로세서 루트의 목록이 있습니다. 메서드는이 메서드가 반환 되기 전에 스케줄러에 대 한 콜백 호출 됩니다.  
  
 스케줄러는 매개 변수를 설정 하 여 현재 스레드에 대 한 구독을 요청 하는 경우 `doSubscribeCurrentThread` 를 `true`, 메서드는 `IExecutionResource` 인터페이스입니다. 구독을 나중에 사용 하 여 종료 해야는 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드.  
  
 하드웨어 스레드 선택을 결정할 때 리소스 관리자는 프로세서 노드 선호도 대 한 최적화 하려고 합니다. 현재 스레드에 대 한 구독이 요청 되는 의도이 스케줄러에 할당 된 작업에 참여 하는 현재 스레드를 나타냅니다. 이 경우 할당 된 가상 프로세서 루트는 현재 스레드가 실행 되 고, 가능한 경우 프로세서 노드에 있습니다.  
  
 스레드의 기본 하드웨어 스레드의 구독 수준이 하나 증가 합니다. 구독이 종료 되 면 구독 수준은 하나씩 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="a-nameshutdowna--ischedulerproxyshutdown-method"></a><a name="shutdown"></a>Ischedulerproxy:: Shutdown 메서드  
 스케줄러가 종료 되는 리소스 관리자에 알립니다. 이렇게 하면 리소스 관리자에서 스케줄러에 부여 된 모든 리소스를 즉시 회수를 합니다.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>주의  
 모든 `IExecutionContext` 메서드를 사용 하는 외부 스레드가 가입의 결과로 받은 스케줄러와 인터페이스 `ISchedulerProxy::RequestInitialVirtualProcessors` 또는 `ISchedulerProxy::SubscribeCurrentThread` 를 리소스 관리자를 반환 합니다를 사용 하 여 `IExecutionResource::Remove` 전에 스케줄러를 종료 합니다.  
  
 스케줄러 있으면 모든 가상 프로세서 루트를 비활성화, 활성화 해야 합니다를 사용 하 여 [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate), 있고 둡니다 에서도 실행 스레드 프록시는 `Dispatch` 메서드 호출 전에 디스패치 하는 이러한 실행 컨텍스트의 `Shutdown` 스케줄러 프록시에 있습니다.  
  
 모든 가상 프로세서 루트는 종료 시 리소스 관리자로 반환되기 때문에 리소스 관리자가 `Remove` 메서드 호출을 통해 부여한 모든 가상 프로세서 루트를 스케줄러가 개별적으로 반환할 필요는 없습니다.  
  
##  <a name="a-namesubscribecurrentthreada--ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>Ischedulerproxy:: Subscribecurrentthread 메서드  
 현재 스레드의 리소스 관리자를이 스케줄러와 연결을 등록 합니다.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IExecutionResource` 런타임의 현재 스레드를 나타내는 상호 작용 합니다.  
  
### <a name="remarks"></a>주의  
 리소스 관리자에서 스케줄러 및 다른 스케줄러에 리소스를 할당 하는 동안 현재 스레드를 고려 하는 경우이 메서드를 사용 합니다. 스케줄러 받는 리소스 관리자에서 가상 프로세서 루트와 함께 사용자의 스케줄러에 작업에 참여 하는 스레드 계획 대기 하는 경우에 특히 유용 합니다. 리소스 관리자는 불필요 한 시스템에 하드웨어 스레드의 초과 구독을 방지 하기 위해 정보를 사용 합니다.  
  
 이 메서드를 통해 받은 실행 리소스를 반환할 리소스 관리자를 사용 하 여는 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드. 호출 하는 스레드는 `Remove` 메서드 호출 이전에 동일한 스레드에서 해야는 `SubscribeCurrentThread` 메서드.  
  
 스레드의 기본 하드웨어 스레드의 구독 수준이 하나 증가 합니다. 구독이 종료 되 면 구독 수준은 하나씩 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="a-nameunbindcontexta--ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>Ischedulerproxy:: Unbindcontext 메서드  
 지정한 실행 컨텍스트에서 스레드 프록시 연결을 해제는 `pContext` 매개 변수 스레드 프록시 팩터리의 사용 가능한 풀으로 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된에 호출할 수 있습니다는 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 고를 통해 아직 시작 되지 않은 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 연결을 끊을 스레드 프록시에서 사용 되는 실행 컨텍스트.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IScheduler 구조체](ischeduler-structure.md)   
 [IThreadProxy 구조체](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)   
 [IResourceManager 구조체](iresourcemanager-structure.md)

