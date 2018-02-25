---
title: "IExecutionContext 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd8b00f24970e6bbc7f582f795c26ccb96461028
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 구조체
지정된 가상 프로세서에서 실행되고 협조적으로 컨텍스트가 전환될 수 있는 실행 컨텍스트에 대한 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IExecutionContext::Dispatch](#dispatch)|스레드 프록시 특정 실행 컨텍스트를 실행이 시작 될 때 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴 이어야 합니다.|  
|[IExecutionContext::GetId](#getid)|실행 컨텍스트에 대 한 고유 식별자를 반환합니다.|  
|[IExecutionContext::GetProxy](#getproxy)|이 컨텍스트에서 실행 되 고 있는 스레드 프록시 인터페이스를 반환 합니다.|  
|[IExecutionContext::GetScheduler](#getscheduler)|스케줄러에 한 인터페이스를 반환이 실행 컨텍스트에 속해 있습니다.|  
|[IExecutionContext::SetProxy](#setproxy)|이 실행 컨텍스트는 스레드 프록시에 연결합니다. 관련 된 스레드 프록시는 컨텍스트를 실행 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.|  
  
## <a name="remarks"></a>설명  
 동시성 런타임의 리소스 관리자와 교류 하는 사용자 지정 스케줄러를 구현 하는 경우 구현 해야 합니다는 `IExecutionContext` 인터페이스입니다. 실행 하 여 사용자의 스케줄러 대신 작업을 수행 하는 리소스 관리자가 만든 스레드는 `IExecutionContext::Dispatch` 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IExecutionContext`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dispatch"></a>  IExecutionContext::Dispatch Method  
 스레드 프록시 특정 실행 컨텍스트를 실행이 시작 될 때 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴 이어야 합니다.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pDispatchState`  
 이 실행 컨텍스트를 디스패치 하는 상태에 대 한 포인터입니다. 디스패치 상태에 대 한 자세한 내용은 참조 하십시오. [DispatchState](dispatchstate-structure.md)합니다.  
  
##  <a name="getid"></a>  IExecutionContext::GetId Method  
 실행 컨텍스트에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 고유 정수 식별자입니다.  
  
### <a name="remarks"></a>설명  
 메서드를 사용 해야 `GetExecutionContextId` 구현 하는 개체에 대 한 고유 식별자를 가져오려면는 `IExecutionContext` 인터페이스를 하는 메서드에 매개 변수로 인터페이스를 사용 하기 전에 리소스 관리자가 제공 합니다. 동일한 식별자를 반환할 때는 `GetId` 함수를 호출 합니다.  
  
 다른 소스에서 가져온 식별자는 정의 되지 않은 동작이 발생할 수 있습니다.  
  
##  <a name="getproxy"></a>  Iexecutioncontext:: Getproxy 메서드  
 이 컨텍스트에서 실행 되 고 있는 스레드 프록시 인터페이스를 반환 합니다.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IThreadProxy` 인터페이스입니다. 실행 컨텍스트 스레드 프록시를 호출 하 여 초기화 되지 않은 경우 `SetProxy`, 함수 반환 해야 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자는 호출는 `SetProxy` 메서드는 실행 컨텍스트를와 `IThreadProxy` 인터페이스를 입력 하기 전에 매개 변수로 `Dispatch` 에서 메서드는 컨텍스트에 합니다. 이 인수를 저장 하 고 호출에서 반환 해야 `GetProxy()`합니다.  
  
##  <a name="getscheduler"></a>  Iexecutioncontext:: Getscheduler 메서드  
 스케줄러에 한 인터페이스를 반환이 실행 컨텍스트에 속해 있습니다.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IScheduler` 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 유효한 실행 컨텍스트를 초기화 해야 `IScheduler` 인터페이스 하는 메서드에 매개 변수로 사용 하기 전에 리소스 관리자가 제공 합니다.  
  
##  <a name="setproxy"></a>  Iexecutioncontext:: Setproxy 메서드  
 이 실행 컨텍스트는 스레드 프록시에 연결합니다. 관련 된 스레드 프록시는 컨텍스트를 실행 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pThreadProxy`  
 스레드 프록시를 입력에 대 한 인터페이스는 `Dispatch` 메서드가 실행 컨텍스트를 합니다.  
  
### <a name="remarks"></a>설명  
 매개 변수를 저장 했던 `pThreadProxy` 에 대 한 호출에서 반환 하 고는 `GetProxy` 메서드. 리소스 관리자 하면 스레드 프록시가 실행 컨텍스트와 관련 된 스레드 프록시가 실행 되는 동안 변경 되지 것입니다는 `Dispatch` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IScheduler 구조체](ischeduler-structure.md)   
 [IThreadProxy 구조체](ithreadproxy-structure.md)
