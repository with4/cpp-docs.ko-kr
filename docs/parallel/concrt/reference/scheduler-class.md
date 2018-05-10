---
title: Scheduler 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97abec33d5fa4b372bc26874fd37397a2b78bb29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="scheduler-class"></a>Scheduler 클래스
동시성 런타임 스케줄러에 대한 추상화를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class Scheduler;
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Scheduler](#ctor)|개체는 `Scheduler` 으로만 팩터리 메서드를 사용 하 여 만들 수 있습니다 하는 클래스 또는 암시적으로 합니다.|  
|[~ Scheduler 소멸자](#dtor)|개체는 `Scheduler` 클래스는 모든 외부 참조가 더 이상 존재 하지 않을 때 암시적으로 제거 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Attach](#attach)|스케줄러 호출 컨텍스트에 연결합니다. 이 메서드가 반환 된 후 호출 컨텍스트에 스케줄러에 의해 관리 되며 스케줄러 현재 스케줄러입니다.|  
|[만들기](#create)|해당 동작을 설명 하 여 새 스케줄러를 만들고는 `_Policy` 매개 변수를 초기 참조는 스케줄러에 배치 하 고를 대 한 포인터를 반환 합니다.|  
|[CreateScheduleGroup](#createschedulegroup)|오버로드됨. 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수로 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.|  
|[GetPolicy](#getpolicy)|사용 하 여 만든 스케줄러 정책의 복사본을 반환 합니다.|  
|[Id](#id)|스케줄러에 대 한 고유 식별자를 반환합니다.|  
|[IsAvailableLocation](#isavailablelocation)|지정된 된 위치를 스케줄러에서 사용할 수 있는지 여부를 결정 합니다.|  
|[참조](#reference)|스케줄러 참조 횟수를 증가 시킵니다.|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows 이벤트 핸들에 전달 된 `_Event` 매개 변수는 스케줄러가 종료 되 고 소멸 때 신호를 받는를 합니다. 이벤트는 동시에 스케줄러에 예약 된 모든 작업이 완료 되었습니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.|  
|[릴리스](#release)|스케줄러 참조 횟수를 감소시킵니다.|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|기본 스케줄러 정책을 런타임 기본값으로 다시 설정합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정이 사용 됩니다.|  
|[ScheduleTask](#scheduletask)|오버로드됨. 스케줄러 내에서 간단한 작업을 예약합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 프로세스 내에서 기본 스케줄러가 없는 경우에이 메서드를 호출할 수 있습니다. 기본 정책이 설정 된 상태로 유지 됩니다. 적용 하거나 다음 유효한 호출 될 때까지 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.|  
  
## <a name="remarks"></a>설명  
 동시성 런타임 스케줄러는 스레드와 같은 운영 체제 실행 컨텍스트에 매핑되는 실행 컨텍스트를 사용 하 여, 작업을 실행 큐에 추가한 응용 프로그램입니다. 언제 든 지 동시성 수준 스케줄러의 리소스 관리자가 부여 하는 가상 프로세서의 수와 같습니다. 가상 프로세서에는 처리 리소스 및 기본 시스템 하드웨어 스레드로 맵에 대 한 추상화입니다. 지정된 된 시간에는 단일 스케줄러 컨텍스트는 가상 프로세서에서 실행할 수 있습니다.  
  
 동시성 런타임의 병렬 작업을 실행 하려면 프로세스 마다 기본 스케줄러를 만듭니다. 또한 사용자 고유의 스케줄러 인스턴스를 만들 하 고이 클래스를 사용 하 여 조작할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Scheduler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="attach"></a> 연결 

 스케줄러 호출 컨텍스트에 연결합니다. 이 메서드가 반환 된 후 호출 컨텍스트에 스케줄러에 의해 관리 되며 스케줄러 현재 스케줄러입니다.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>설명  
 스케줄러를 연결 하면 암시적으로 스케줄러에 대 한 참조를 배치 합니다.  
  
 특정 시점에 나중에 호출 해야 합니다는 [currentscheduler:: Detach](currentscheduler-class.md#detach) 메서드를 종료 하려면 스케줄러 수 있도록 합니다.  
  
 이 메서드는 다른 스케줄러에 이미 연결 되어 있는 컨텍스트에서 이전 스케줄러로 기존 스케줄러 기억 됩니다 및 새로 만든 스케줄러가 현재 스케줄러입니다. 호출 하는 경우는 `CurrentScheduler::Detach` 이전 스케줄러 나중 시점 메서드는 현재 스케줄러로 복원 됩니다.  
  
 이 메서드는 throw 된 [improper_scheduler_attach](improper-scheduler-attach-class.md) 이 스케줄러는 호출 컨텍스트에의 현재 스케줄러 경우 예외입니다.  
  
##  <a name="create"></a> 만들기 

 해당 동작을 설명 하 여 새 스케줄러를 만들고는 `_Policy` 매개 변수를 초기 참조는 스케줄러에 배치 하 고를 대 한 포인터를 반환 합니다.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Policy`  
 새로 만든된 스케줄러의 동작을 설명 하는 스케줄러 정책.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 스케줄러에 대 한 포인터입니다. 이 `Scheduler` 개체에 배치 하 여 초기 참조 횟수입니다.  
  
### <a name="remarks"></a>설명  
 스케줄러를 사용 하 여 만들어집니다. 후의 `Create` 호출 해야 합니다는 `Release` 초기 참조 횟수를 제거 하 고 종료 하려면 스케줄러를 허용 하기 위해 나중에 특정 시점에 메서드.  
  
 이 메서드를 사용 하 여 만든 스케줄러 호출 컨텍스트에 연결 되지 않습니다. 컨텍스트를 사용 하 여 연결할 수 있습니다는 [연결](#attach) 메서드.  
  
 이 메서드는 다양 한 예외를 포함 하 여 throw 할 수 있습니다 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) 및 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)합니다.  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수로 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 있는 위치는 일정 그룹 내의 태스크는 실행에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 일정 그룹에 대 한 포인터입니다. 이 `ScheduleGroup` 개체에 배치 하 여 초기 참조 횟수입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야는 [릴리스](schedulegroup-class.md#release) 예약 작업을 완료 하는 일정 그룹에는 메서드. 스케줄러에 일정 손상 되므로 그룹의 모든 작업을 큐에 대기 중이면 완료 합니다.  
  
 참고가이 스케줄러를 명시적으로 만든 스케줄러의 참조를 해제 하기 전에 그 안에 있는 그룹을 예약 하는 모든 참조 해제 해야 합니다.  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러에 대 한 가상 프로세서의 현재 수입니다.  
  
##  <a name="getpolicy"></a> GetPolicy 

 사용 하 여 만든 스케줄러 정책의 복사본을 반환 합니다.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 사용 하 여 만든 스케줄러 정책의 복사본입니다.  
  
##  <a name="id"></a> Id 

 스케줄러에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러에 대 한 고유 식별자입니다.  
  
##  <a name="isavailablelocation"></a> IsAvailableLocation 

 지정된 된 위치를 스케줄러에서 사용할 수 있는지 여부를 결정 합니다.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 에 대 한 스케줄러를 쿼리 하는 위치에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치 여부를 나타내는 값의 `_Placement` 인수는 스케줄러에서 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 지정된 위치를 사용할 수 있는지 여부의 순간 샘플링입니다. 여러 스케줄러가 있으면 동적 자원 관리에서 어느 시점에 스케줄러의 리소스를 추가하거나 제거할 수 있습니다. 이 경우 지정된 위치의 가용성이 변경될 수 있습니다.  
  
##  <a name="reference"></a> 참조 

 스케줄러 참조 횟수를 증가 시킵니다.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>반환 값  
 새로 증가 참조 횟수입니다.  
  
### <a name="remarks"></a>설명  
 이 구성에 대 한 스케줄러의 수명을 관리 하 고 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가 0이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.  
  
 합니다는 [improper_scheduler_reference](improper-scheduler-reference-class.md) 참조 횟수를 호출 하기 전에 경우 예외는 `Reference` 메서드 0이 되어 스케줄러에서 소유 하지 않은 컨텍스트를 호출 합니다.  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Windows 이벤트 핸들에 전달 된 `_Event` 매개 변수는 스케줄러가 종료 되 고 소멸 때 신호를 받는를 합니다. 이벤트는 동시에 스케줄러에 예약 된 모든 작업이 완료 되었습니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Event`  
 스케줄러를 종료 하 고 자체를 제거 하는 경우 런타임에 하 여 알릴 수 있는 Windows 이벤트 개체에 대 한 핸들입니다.  
  
##  <a name="release"></a> 릴리스 

 스케줄러 참조 횟수를 감소시킵니다.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새로 감소 참조 횟수입니다.  
  
### <a name="remarks"></a>설명  
 이 구성에 대 한 스케줄러의 수명을 관리 하 고 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가 0이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.  
  
##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy 

 기본 스케줄러 정책을 런타임 기본값으로 다시 설정합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정이 사용 됩니다.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>설명  
 기본 스케줄러 프로세스 내에 존재 하는 동안이 메서드를 호출할 수 있습니다. 기존의 기본 스케줄러 정책에는 영향을 주지 않습니다. 그러나, 기본 스케줄러를 종료 된 경우 새 기본 나중에 생성 된 새 스케줄러 런타임 기본 정책 설정을 사용 합니다.  
  
##  <a name="ctor"></a> 스케줄러 

 개체는 `Scheduler` 으로만 팩터리 메서드를 사용 하 여 만들 수 있습니다 하는 클래스 또는 암시적으로 합니다.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>설명  
 프로세스의 기본 스케줄러는 여러 호출 컨텍스트에 연결 하는 스케줄러 해야 하는 런타임 함수를 이용할 때 암시적으로 생성 됩니다. 내에서 메서드는 `CurrentScheduler` 클래스 및 PPL 및 에이전트 레이어의 기능 암시적 첨부 파일을 일반적으로 수행 합니다.  
  
 중 하나를 통해 명시적으로 스케줄러를 만들 수도 있습니다는 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 메서드.  
  
##  <a name="dtor"></a> ~ 스케줄러 

 개체는 `Scheduler` 클래스는 모든 외부 참조가 더 이상 존재 하지 않을 때 암시적으로 제거 됩니다.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 스케줄러 내에서 간단한 작업을 예약합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Proc`  
 간단한 작업의 본문을 수행 하기 위해 실행할 함수에 대 한 포인터입니다.  
  
 `_Data`  
 작업의 본문에 매개 변수로 전달 되는 데이터에 대 한 void 포인터입니다.  
  
 `_Placement`  
 간단한 작업이 실행될 수 있는 위치에 대한 참조입니다.  
  
##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy 

 사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 프로세스 내에서 기본 스케줄러가 없는 경우에이 메서드를 호출할 수 있습니다. 기본 정책이 설정 된 상태로 유지 됩니다. 적용 하거나 다음 유효한 호출 될 때까지 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Policy`  
 기본 스케줄러 정책으로 설정 하는 정책입니다.  
  
### <a name="remarks"></a>설명  
 경우는 `SetDefaultSchedulerPolicy` 프로세스 내에서 기본 스케줄러를 이미 있는 경우 메서드가 호출 되 면 런타임에서 throw 됩니다는 [default_scheduler_exists](default-scheduler-exists-class.md) 예외입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [Scheduler 클래스](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



