---
title: "IExecutionResource 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fa3c65780ac9e001e6f6b8a015dc7f70df47181f
ms.lasthandoff: 03/17/2017

---
# <a name="iexecutionresource-structure"></a>IExecutionResource 구조체
하드웨어 스레드에 대한 추상화입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Iexecutionresource:: Currentsubscriptionlevel](#currentsubscriptionlevel)|활성화 된 가상 프로세서 수가 루트 및 구독 한 현재 스레드와 연결 된 기본 하드웨어가 실행 리소스가 나타내는 외부 스레드를 반환 합니다.|  
|[Iexecutionresource:: Getexecutionresourceid](#getexecutionresourceid)|이 실행 리소스를 나타내는 하드웨어 스레드에 대 한 고유 식별자를 반환 합니다.|  
|[Iexecutionresource:: Getnodeid](#getnodeid)|이 실행 리소스가 속한 프로세서 노드에 대 한 고유 식별자를 반환 합니다.|  
|[Iexecutionresource:: Remove](#remove)|이 실행 리소스를 리소스 관리자를 반환합니다.|  
  
## <a name="remarks"></a>주의  
 실행 리소스 취득 가능 또는 가상 프로세서 루트와 연결 합니다. 독립 실행형 실행 리소스는 응용 프로그램의 스레드는 스레드 구독을 만들 때 생성 됩니다. 메서드 [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) 및 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 스레드 구독을 만들고 반환 된 `IExecutionResource` 구독을 나타내는 인터페이스입니다. 스레드 구독을 만드는 알리는 작업에 지정된 된 스레드가 참가할 리소스 관리자 리소스 관리자를 스케줄러에 할당 된 가상 프로세서 루트와 함께 스케줄러에 큐에 대기 됩니다. 리소스 관리자를 사용 클라우드 하드웨어 스레드를 방지 하려면 수 없는 정보입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IExecutionResource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="currentsubscriptionlevel"></a>Iexecutionresource:: Currentsubscriptionlevel 메서드  
 활성화 된 가상 프로세서 수가 루트 및 구독 한 현재 스레드와 연결 된 기본 하드웨어가 실행 리소스가 나타내는 외부 스레드를 반환 합니다.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 현재 구독 수준입니다.  
  
### <a name="remarks"></a>주의  
 실행 중인 스레드 수는 하드웨어 스레드와 연결 된 구독 수준에서 알 수 있습니다. 이 스레드는 리소스 관리자는 구독 된 스레드 및 스레드 프록시를 현재 실행 중인 가상 프로세서 루트의 형태로 인식에 포함 됩니다.  
  
 메서드를 호출 하면 [ischedulerproxy:: Subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread), 메서드 또는 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 매개 변수와 함께 `doSubscribeCurrentThread` 값으로 설정 `true` 구독 수준의 하드웨어 스레드를 하나 증가 시킴 합니다. 반환 한다는 점에서 `IExecutionResource` 구독을 나타내는 인터페이스입니다. 해당 호출의 [iexecutionresource:: Remove](#remove) 감소 씩 하드웨어 스레드의 구독 수준입니다.  
  
 메서드를 사용 하는 가상 프로세서 루트를 활성화 하는 작업 [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate) 하드웨어 스레드의 구독 수준 씩 증가 시킵니다. 메서드 [ivirtualprocessorroot:: Deactivate](ivirtualprocessorroot-structure.md#deactivate), 또는 [iexecutionresource:: Remove](#remove) 구독 수준을 활성화 된 가상 프로세서 루트에서 호출 될 때&1; 씩 감소 합니다.  
  
 리소스 관리자는 스케줄러 간에 리소스를 이동 하는 시기를 결정 하는 방법 중 하나로 구독 수준 정보를 사용 합니다.  
  
##  <a name="getexecutionresourceid"></a>Iexecutionresource:: Getexecutionresourceid 메서드  
 이 실행 리소스를 나타내는 하드웨어 스레드에 대 한 고유 식별자를 반환 합니다.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 이 실행 리소스 내부 하드웨어 스레드에 대 한 고유 식별자입니다.  
  
### <a name="remarks"></a>주의  
 각 하드웨어 스레드는 동시성 런타임에서 고유 식별자를 할당 됩니다. 연결 된 하드웨어는 여러 실행 리소스 경우 스레드를 갖게 됩니다 동일한 실행 리소스 식별자입니다.  
  
##  <a name="getnodeid"></a>Iexecutionresource:: Getnodeid 메서드  
 이 실행 리소스가 속한 프로세서 노드에 대 한 고유 식별자를 반환 합니다.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 프로세서 노드에 대 한 고유 식별자입니다.  
  
### <a name="remarks"></a>주의  
 동시성 런타임에서는 프로세서 노드 그룹에 있는 시스템에 있는 하드웨어 스레드를 나타냅니다. 노드는 일반적으로 시스템의 하드웨어 토폴로지에에서 파생 됩니다. 예를 들어 동일한 프로세서 노드에서 특정 NUMA 노드 또는 특정 소켓에 있는 모든 프로세서 속할 수 있습니다. 부터는이 노드를 고유 식별자를 할당 하는 리소스 관리자 `0` 까지 포함 하 여 `nodeCount - 1`여기서 `nodeCount` 시스템에서 프로세서 노드의 총 수를 나타냅니다.  
  
 함수에서 노드 수를 얻을 수 있습니다 [GetProcessorNodeCount](concurrency-namespace-functions.md)합니다.  
  
##  <a name="remove"></a>Iexecutionresource:: Remove 메서드  
 이 실행 리소스를 리소스 관리자를 반환합니다.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pScheduler`  
 이 실행 리소스 제거를 요청 하는 스케줄러에 대 한 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 독립 실행형 실행 리소스 및 리소스 관리자에 가상 프로세서 루트와 연결 된 실행 리소스를 반환 합니다.  
  
 방법 중 하나에서 수신 하는 경우이 독립 실행형 실행 리소스 [ischedulerproxy:: Subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread) 또는 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), 메서드를 호출 하면 `Remove` 리소스를 만든 스레드 구독 종료 됩니다 나타냅니다. 스케줄러 프록시를 종료 하기 전에 모든 스레드 구독을 종료 하는 데 필요한 및 호출 해야 `Remove` 구독을 만든 스레드에서 합니다.  
  
 인터페이스 `Remove`는 `IVirtualProcessorRoot` 인터페이스에서 상속되기 때문에 `IExecutionResource` 메서드를 호출하여 리소스 관리자에 가상 프로세서 루트도 반환할 수 있습니다. 가상 프로세서 루트에 대 한 호출에 대 한 응답으로 반환 하도록 할 수는 [ischeduler:: Removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors) 메서드를에서 가져온 프로그램으로 가상 프로세서 루트를 마칠 때 또는 [ischedulerproxy:: Createoversubscriber](ischedulerproxy-structure.md#createoversubscriber) 메서드. 가상 프로세서 루트에 대 한 제한은 없습니다 스레드를 호출할 수는 `Remove` 메서드.  
  
 `invalid_argument`경우 throw 되는 매개 변수 `pScheduler` 로 설정 된 `NULL`합니다.  
  
 `invalid_operation`없으면 예외가 매개 변수 `pScheduler` 는 현재 스레드가 스레드 구독을 만든 스레드가 아닌 다른 경우, 또는 독립 실행형 실행 리소스와 함께이 실행 리소스를 만든 스케줄러 다릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)

