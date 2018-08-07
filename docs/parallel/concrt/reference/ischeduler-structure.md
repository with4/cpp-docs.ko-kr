---
title: IScheduler 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c78d02ccd5639369ad8b4d0183458da2ba85269
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693993"
---
# <a name="ischeduler-structure"></a>IScheduler 구조체
작업 스케줄러의 추상화에 대한 인터페이스입니다. 동시성 런타임의 리소스 관리자는 이 인터페이스를 사용하여 작업 스케줄러와 통신합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|용도 맞게 가상 프로세서 루트의 집합으로 스케줄러를 제공 합니다. 각 `IVirtualProcessorRoot` 인터페이스 대신 스케줄러 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.|  
|[IScheduler::GetId](#getid)|스케줄러에 대 한 고유 식별자를 반환합니다.|  
|[IScheduler::GetPolicy](#getpolicy)|스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하십시오. [SchedulerPolicy](schedulerpolicy-class.md)합니다.|  
|[IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|배열에서 가상 프로세서 루트의 집합에 의해 표현 되는 하드웨어 스레드가이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 현재 사용 되 고 있습니다.|  
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|배열에서 가상 프로세서 루트의 집합에 의해 표현 되는 하드웨어 스레드가이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 사용 되지 않습니다.|  
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|이 스케줄러에 이전에 할당 된 가상 프로세서 루트의 제거를 시작 합니다.|  
|[Ischeduler:: Statistics](#statistics)|작업 도착과 완료 속도 및 스케줄러에 대 한 변경의 큐 길이 관련 된 정보를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 리소스 관리자와 통신 하는 사용자 지정 스케줄러를 구현 하는 경우에 구현을 제공 해야는 `IScheduler` 인터페이스입니다. 이 인터페이스는 양방향 채널 스케줄러와 리소스 관리자 간의 통신의 한쪽 끝입니다. 다른 쪽 끝으로 표시 됩니다는 `IResourceManager` 및 `ISchedulerProxy` 리소스 관리자에 의해 구현 되는 인터페이스입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IScheduler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="addvirtualprocessors"></a>  Ischeduler:: Addvirtualprocessors 메서드  
 용도 맞게 가상 프로세서 루트의 집합으로 스케줄러를 제공 합니다. 각 `IVirtualProcessorRoot` 인터페이스 대신 스케줄러 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `ppVirtualProcessorRoots`  
 배열 `IVirtualProcessorRoot` 가상 프로세서를 나타내는 인터페이스 루트 스케줄러에 추가 되 고 있습니다.  
  
 `count`  
 수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자를 호출 하는 `AddVirtualProcessor` 스케줄러에 가상 프로세서 루트의 초기 집합을 부여 하는 메서드. 스케줄러 간에 리소스를 변경 하는 경우 스케줄러에 가상 프로세서 루트를 추가 하려면 메서드는 호출 또한 수 있습니다.  
  
##  <a name="getid"></a>  Ischeduler:: Getid 메서드  
 스케줄러에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 고유 정수 식별자입니다.  
  
### <a name="remarks"></a>설명  
 사용 해야는 [GetSchedulerId](concurrency-namespace-functions.md) 구현 하는 개체에 대 한 고유 식별자를 가져오는 함수는 `IScheduler` 인터페이스를 하는 메서드에 매개 변수로 인터페이스를 사용 하기 전에 리소스 관리자가 제공 합니다. 동일한 식별자를 반환할 때는 `GetId` 함수를 호출 합니다.  
  
 다른 소스에서 가져온 식별자는 정의 되지 않은 동작이 발생할 수 있습니다.  
  
##  <a name="getpolicy"></a>  Ischeduler:: Getpolicy 메서드  
 스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하십시오. [SchedulerPolicy](schedulerpolicy-class.md)합니다.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러 정책의 복사본입니다.  
  
##  <a name="notifyresourcesexternallybusy"></a>  Ischeduler:: Notifyresourcesexternallybusy 메서드  
 배열에서 가상 프로세서 루트의 집합에 의해 표현 되는 하드웨어 스레드가이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 현재 사용 되 고 있습니다.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `ppVirtualProcessorRoots`  
 배열 `IVirtualProcessorRoot` 다른 스케줄러 사용 중 상태가 된 있는 하드웨어 스레드와 관련 된 인터페이스입니다.  
  
 `count`  
 수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수에 대 한 것 같습니다. 이 대 한 한 가지 이유 않은지 충분 한 하드웨어 스레드 리소스를 공유 하지 않고 모든 스케줄러에 대 한 최소 동시성을 충족 하기 위해 시스템에 수 있습니다. 또 다른 원인은 해제 하 고 해당 하드웨어 스레드에서 모든 가상 프로세서 루트를 통해 그를 소유 하는 스케줄러는 사용 하지 않는 경우 리소스 다른 스케줄러에는 할당 일시적으로 됩니다.  
  
 하드웨어 스레드 구독 수준 구독 된 스레드 수로 표시 됩니다 및 해당 하드웨어 스레드와 연결 된 가상 프로세서 루트를 활성화 합니다. 특정 스케줄러의 관점에서의 하드웨어 스레드 외부 구독 수준에는 구독에 영향을 다른 스케줄러의 부분입니다. 알림 리소스는 외부에서 사용 중인 하드웨어 스레드에 대 한 외부 구독 수준 양수 territory에 0에서 이동 하면 스케줄러에 전송 됩니다.  
  
 이 메서드를 통해 알림을 정책이 스케줄러에만 전송 됩니다 위치에 대 한 값의 `MinConcurrency` 정책 키에 대 한 값과 같은는 `MaxConcurrency` 정책 키입니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하십시오. [SchedulerPolicy](schedulerpolicy-class.md)합니다.  
  
 알림에 대 한 정하는 스케줄러는 집합을 가져옵니다 초기 알림 만들어질 때만 할당 된 리소스는 외부에서 사용 중인지 또는 유휴 여부를 알립니다.  
  
##  <a name="notifyresourcesexternallyidle"></a>  Ischeduler:: Notifyresourcesexternallyidle 메서드  
 배열에서 가상 프로세서 루트의 집합에 의해 표현 되는 하드웨어 스레드가이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 사용 되지 않습니다.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `ppVirtualProcessorRoots`  
 배열 `IVirtualProcessorRoot` 하드웨어 스레드를 다른 스케줄러가 유휴 상태가 된와 관련 된 인터페이스입니다.  
  
 `count`  
 수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수에 대 한 것 같습니다. 이 대 한 한 가지 이유 않은지 충분 한 하드웨어 스레드 리소스를 공유 하지 않고 모든 스케줄러에 대 한 최소 동시성을 충족 하기 위해 시스템에 수 있습니다. 또 다른 원인은 해제 하 고 해당 하드웨어 스레드에서 모든 가상 프로세서 루트를 통해 그를 소유 하는 스케줄러는 사용 하지 않는 경우 리소스 다른 스케줄러에는 할당 일시적으로 됩니다.  
  
 하드웨어 스레드 구독 수준 구독 된 스레드 수로 표시 됩니다 및 해당 하드웨어 스레드와 연결 된 가상 프로세서 루트를 활성화 합니다. 특정 스케줄러의 관점에서의 하드웨어 스레드 외부 구독 수준에는 구독에 영향을 다른 스케줄러의 부분입니다. 알림 리소스는 외부에서 사용 중인 하드웨어 스레드에 대 한 외부 구독 수준에서 이전 양수 값을 0으로 떨어질 때 스케줄러에 전송 됩니다.  
  
 이 메서드를 통해 알림을 정책이 스케줄러에만 전송 됩니다 위치에 대 한 값의 `MinConcurrency` 정책 키에 대 한 값과 같은는 `MaxConcurrency` 정책 키입니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하십시오. [SchedulerPolicy](schedulerpolicy-class.md)합니다.  
  
 알림에 대 한 정하는 스케줄러는 집합을 가져옵니다 초기 알림 만들어질 때만 할당 된 리소스는 외부에서 사용 중인지 또는 유휴 여부를 알립니다.  
  
##  <a name="removevirtualprocessors"></a>  Ischeduler:: Removevirtualprocessors 메서드  
 이 스케줄러에 이전에 할당 된 가상 프로세서 루트의 제거를 시작 합니다.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `ppVirtualProcessorRoots`  
 배열 `IVirtualProcessorRoot` 제거할 가상 프로세서 루트를 나타내는 인터페이스입니다.  
  
 `count`  
 수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자를 호출 하는 `RemoveVirtualProcessors` 스케줄러에서 다시 가상 프로세서 루트의 집합을 수행 하는 메서드. 스케줄러를 호출 하는 예상 되는 [제거](iexecutionresource-structure.md#remove) 가상 프로세서 루트와 수행 되는 경우 각 인터페이스에서 메서드. 사용 하지 않는 한 `IVirtualProcessorRoot` 호출한 후 인터페이스는 `Remove` 메서드를 합니다.  
  
 매개 변수 `ppVirtualProcessorRoots` 인터페이스의 배열을 가리킵니다. 제거할 가상 프로세서 루트의 집합 중에 활성화 되지 않은 루트의 경우 사용 하 여 즉시 반환 될 수는 `Remove` 메서드. 활성화 하 고 작업을 실행 중이거나 또는 비활성화 된 것 이며 있는 도착 하는 작업에 대 한 대기 중인 루트를 비동기적으로 반환 되어야 합니다. 스케줄러에는 최대한 빨리 가상 프로세서 루트를 제거 하려고 할 때마다 확인 해야 합니다. 가상 프로세서 루트의 제거를 연기 스케줄러 내에서 의도 하지 않은 초과 될 수 있습니다.  
  
##  <a name="statistics"></a>  Ischeduler:: Statistics 메서드  
 작업 도착과 완료 속도 및 스케줄러에 대 한 변경의 큐 길이 관련 된 정보를 제공 합니다.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pTaskCompletionRate`  
 이 메서드에 대 한 마지막 호출 후 스케줄러에서 완료 된 작업의 수입니다.  
  
 `pTaskArrivalRate`  
 이 메서드에 대 한 마지막 호출 후 스케줄러에 도착 한 작업의 수입니다.  
  
 `pNumberOfTasksEnqueued`  
 모든 스케줄러 큐에 작업의 총 수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 스케줄러에 대 한 통계를 수집 하려면 리소스 관리자에 의해 호출 됩니다. 여기에 수집 된 통계를 스케줄러에 더 많은 리소스를 할당 하려면 적절 한 경우와 시기 시간과 리소스를 결정 하는 동적 피드백 알고리즘을 진행 하는 데 사용 됩니다. 스케줄러에서 제공 되는 값은 최적화 될 수 있으며 반드시 현재 수를 정확 하 게 반영 하도록 합니다.  
  
 리소스 관리자에서 작업 도착 등에 대한 피드백을 사용하여 사용자의 스케줄러와 리소스 관리자에 등록된 다른 스케줄러 간에 리소스 균형을 조정하는 방법을 결정하려면 이 메서드를 구현해야 합니다. 정책 키를 설정할 수 통계를 수집 하지 않도록 선택 `DynamicProgressFeedback` 값 `DynamicProgressFeedbackDisabled` 관리자 스케줄러의 정책 및 리소스에 사용자의 스케줄러에서이 메서드를 호출 하지 것입니다.  
  
 통계 정보가 없는 경우 리소스 관리자 리소스 할당 및 마이그레이션 결정을 내릴 수 하드웨어 스레드 구독 수준을 사용 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy 클래스](schedulerpolicy-class.md)   
 [IExecutionContext 구조체](iexecutioncontext-structure.md)   
 [IThreadProxy 구조체](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)   
 [IResourceManager 구조체](iresourcemanager-structure.md)
