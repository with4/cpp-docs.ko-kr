---
title: "IExecutionContext 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IExecutionContext
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
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
ms.openlocfilehash: 5ad3f21e55371b904ac8a597a7a66d5c5deb8339
ms.lasthandoff: 02/24/2017

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
|[Iexecutioncontext:: Dispatch 메서드](#dispatch)|스레드 프록시는 특정 실행 컨텍스트를 실행이 시작 될 때 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴 이어야 합니다.|  
|[Iexecutioncontext:: Getid 메서드](#getid)|실행 컨텍스트에 대 한 고유 식별자를 반환합니다.|  
|[Iexecutioncontext:: Getproxy 메서드](#getproxy)|이 컨텍스트에서 실행 되 고 있는 스레드 프록시는 인터페이스를 반환 합니다.|  
|[Iexecutioncontext:: Getscheduler 메서드](#getscheduler)|스케줄러에 한 인터페이스를 반환이 실행 컨텍스트에 속해 있습니다.|  
|[Iexecutioncontext:: Setproxy 메서드](#setproxy)|스레드 프록시를이 실행 컨텍스트에 연결합니다. 관련된 스레드 프록시는 컨텍스트를 실행 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.|  
  
## <a name="remarks"></a>주의  
 구현 해야 동시성 런타임의 리소스 관리자와 상호 작용 하는 사용자 지정 스케줄러를 구현 하는 경우는 `IExecutionContext` 인터페이스입니다. 실행 하 여 스케줄러를 대신 하 여 작업을 수행 하는 리소스 관리자에서 만든 스레드는 `IExecutionContext::Dispatch` 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IExecutionContext`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namedispatcha--iexecutioncontextdispatch-method"></a><a name="dispatch"></a>Iexecutioncontext:: Dispatch 메서드  
 스레드 프록시는 특정 실행 컨텍스트를 실행이 시작 될 때 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴 이어야 합니다.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pDispatchState`  
 이 실행 컨텍스트를 디스패치 하는 상태에 대 한 포인터입니다. 디스패치 상태에 대 한 자세한 내용은 참조 하십시오. [DispatchState](dispatchstate-structure.md)합니다.  
  
##  <a name="a-namegetida--iexecutioncontextgetid-method"></a><a name="getid"></a>Iexecutioncontext:: Getid 메서드  
 실행 컨텍스트에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 고유 정수 식별자입니다.  
  
### <a name="remarks"></a>주의  
 메서드를 사용 해야 `GetExecutionContextId` 를 구현 하는 개체에 대 한 고유 식별자를 가져올는 `IExecutionContext` 인터페이스를 하는 메서드에 매개 변수로 인터페이스를 사용 하기 전에 리소스 관리자에서 제공 합니다. 동일한 식별자를 반환 하는 예상 되는 경우는 `GetId` 함수가 호출 됩니다.  
  
 다른 소스에서 가져온 식별자는 정의 되지 않은 동작이 발생할 수 있습니다.  
  
##  <a name="a-namegetproxya--iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>Iexecutioncontext:: Getproxy 메서드  
 이 컨텍스트에서 실행 되 고 있는 스레드 프록시는 인터페이스를 반환 합니다.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IThreadProxy` 인터페이스입니다. 실행 컨텍스트의 스레드 프록시를 호출 하 여 초기화 되지 않은 경우 `SetProxy`, 함수 반환 해야 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 리소스 관리자를 호출 합니다는 `SetProxy` 메서드는 실행 컨텍스트를와 `IThreadProxy` 인터페이스를 입력 하기 전에 매개 변수로 `Dispatch` 메서드는 컨텍스트에 합니다. 이 인수를 저장 하 고에 대 한 호출에서 반환 해야 `GetProxy()`합니다.  
  
##  <a name="a-namegetschedulera--iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>Iexecutioncontext:: Getscheduler 메서드  
 스케줄러에 한 인터페이스를 반환이 실행 컨텍스트에 속해 있습니다.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IScheduler` 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 유효한 실행 컨텍스트를 초기화 해야 하는 `IScheduler` 인터페이스 메서드를 매개 변수로 사용 하기 전에 리소스 관리자에서 제공 합니다.  
  
##  <a name="a-namesetproxya--iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>Iexecutioncontext:: Setproxy 메서드  
 스레드 프록시를이 실행 컨텍스트에 연결합니다. 관련된 스레드 프록시는 컨텍스트를 실행 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pThreadProxy`  
 입력 하는 스레드 프록시에 대 한 인터페이스는 `Dispatch` 이 실행 컨텍스트에 메서드.  
  
### <a name="remarks"></a>주의  
 매개 변수를 저장 해야 `pThreadProxy` 에 대 한 호출에서 반환 하 고는 `GetProxy` 메서드. 리소스 관리자를 사용 하면 스레드 프록시가 실행 되는 동안 실행 컨텍스트에 연결 된 스레드 프록시를 변경 되지 것입니다는 `Dispatch` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IScheduler 구조체](ischeduler-structure.md)   
 [IThreadProxy 구조체](ithreadproxy-structure.md)

