---
title: "Scheduler 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::Scheduler
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: ea4de856528305020e8b082da3a55fcd27df3a64
ms.lasthandoff: 02/24/2017

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
|[스케줄러 생성자](#ctor)|개체는 `Scheduler` 팩터리 메서드를 사용 하 여 만든 클래스 수 또는 암시적으로 합니다.|  
|[~ Scheduler 소멸자](#dtor)|개체는 `Scheduler` 클래스는 모든 외부 참조가 사라질 때 암시적으로 소멸 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Attach 메서드](#attach)|호출 컨텍스트를 스케줄러를 연결합니다. 이 메서드에서 반환 된 후 호출 컨텍스트는 스케줄러에 의해 관리 되며 스케줄러 현재 스케줄러입니다.|  
|[Create 메서드](#create)|해당 동작이 설명 하는 새 스케줄러를 만들고는 `_Policy` 매개 변수를 초기 참조는 스케줄러에 배치 하 고에 대 한 포인터를 반환 합니다.|  
|[CreateScheduleGroup 메서드](#createschedulegroup)|오버로드됨. 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.|  
|[GetNumberOfVirtualProcessors 메서드](#getnumberofvirtualprocessors)|스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.|  
|[GetPolicy 메서드](#getpolicy)|생성 된 스케줄러 정책의 복사본을 반환 합니다.|  
|[Id 메서드](#id)|스케줄러에 대 한 고유 식별자를 반환합니다.|  
|[IsAvailableLocation 메서드](#isavailablelocation)|지정된 된 위치를 스케줄러에서 사용할 수 있는지 여부를 결정 합니다.|  
|[Reference 메서드](#reference)|스케줄러 참조 횟수를 증가 시킵니다.|  
|[RegisterShutdownEvent 메서드](#registershutdownevent)|Windows 이벤트 핸들 변수에 전달은 `_Event` 매개 변수는 스케줄러가 종료 되 고 소멸 때 신호를 보낼 수 있습니다. 이벤트는 동시에 스케줄러에 예약한 하는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.|  
|[Release 메서드](#release)|스케줄러 참조 횟수를 감소시킵니다.|  
|[ResetDefaultSchedulerPolicy 메서드](#resetdefaultschedulerpolicy)|기본 스케줄러 정책을 런타임 기본값으로 다시 설정 합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정을 사용 합니다.|  
|[ScheduleTask 메서드](#scheduletask)|오버로드됨. 스케줄러 내에서 간단한 작업을 예약합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.|  
|[SetDefaultSchedulerPolicy 메서드](#setdefaultschedulerpolicy)|사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 기본 스케줄러가 프로세스 내에 존재 하는 경우에이 메서드를 호출할 수 있습니다. 다음 유효한 호출 될 때까지 적용 됩니다 기본 정책은 설정 된 후의 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.|  
  
## <a name="remarks"></a>주의  
 동시성 런타임에서 스케줄러 스레드 같은 운영 체제 실행 컨텍스트에 매핑되는 실행 컨텍스트를 사용 하 여, 작업을 실행 하 여 큐에 추가한 응용 프로그램입니다. 언제 든 지 스케줄러의 동시성 수준은 리소스 관리자가 부여 하는 가상 프로세서의 수와 같습니다. 가상 프로세서에는 처리 리소스 및 내부 시스템에 대 한 하드웨어 스레드를 맵에 대 한 추상화입니다. 지정된 된 시간에는 단일 스케줄러 컨텍스트는 가상 프로세서에서 실행할 수 있습니다.  
  
 동시성 런타임의 병렬 작업을 실행 하려면 프로세스당 기본 스케줄러를 만듭니다. 또한 사용자 고유의 스케줄러 인스턴스를 만들 하 고이 클래스를 사용 하 여 조작할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Scheduler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameattacha-attach"></a><a name="attach"></a>연결 

 호출 컨텍스트를 스케줄러를 연결합니다. 이 메서드에서 반환 된 후 호출 컨텍스트는 스케줄러에 의해 관리 되며 스케줄러 현재 스케줄러입니다.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>주의  
 스케줄러를 연결 하면 암시적으로 스케줄러에 대 한 참조를 배치 합니다.  
  
 어느 시점 나중에 호출 해야는 [currentscheduler:: Detach](currentscheduler-class.md#detach) 메서드를 종료 하려면 스케줄러 수 있도록 합니다.  
  
 이 메서드는 다른 스케줄러에 이미 연결 되어 있는 컨텍스트를, 기존 스케줄러는 이전 스케줄러로 기억 되 고 새로 만든 스케줄러가 현재 스케줄러. 호출 하는 경우는 `CurrentScheduler::Detach` 메서드는 나중에, 이전 스케줄러를 현재 스케줄러로 복원 됩니다.  
  
 이 메서드는 [improper_scheduler_attach](improper-scheduler-attach-class.md) 이 스케줄러는 현재 스케줄러 호출 컨텍스트의 경우는 예외입니다.  
  
##  <a name="a-namecreatea-create"></a><a name="create"></a>만들기 

 해당 동작이 설명 하는 새 스케줄러를 만들고는 `_Policy` 매개 변수를 초기 참조는 스케줄러에 배치 하 고에 대 한 포인터를 반환 합니다.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Policy`  
 새로 만든된 스케줄러의 동작을 설명 하는 스케줄러 정책.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 스케줄러에 대 한 포인터입니다. 이 `Scheduler` 개체에 배치 하는 초기 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 으로 스케줄러를 만들고 나면는 `Create` 호출 해야 메서드를는 `Release` 초기 참조 횟수를 제거 하 고 종료 하려면 스케줄러를 허용 하기 위해 나중에 특정 시점 메서드.  
  
 이 메서드를 사용 하 여 만든 스케줄러 호출 컨텍스트에 연결 되지 않은 경우 컨텍스트를 사용 하 여 연결할 수는 [연결](#attach) 메서드.  
  
 이 메서드는 다양 한 예외를 포함 하 여 throw 할 수 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) 및 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)합니다.  
  
##  <a name="a-namecreateschedulegroupa-createschedulegroup"></a><a name="createschedulegroup"></a>CreateScheduleGroup 

 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 있는 위치는 일정 그룹 내의 작업은 실행에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 일정 그룹에 대 한 포인터입니다. 이 `ScheduleGroup` 개체에 배치 하는 초기 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 호출 해야는 [릴리스](schedulegroup-class.md#release) 메서드 예약 작업을 완료 하는 일정 그룹에 있습니다. 스케줄러 일정 파기 합니다. 그룹에 큐에 대기 되는 모든 작업 완료 합니다.  
  
 참고가이 스케줄러를 명시적으로 만든 경우 스케줄러에 대 한 참조를 해제 하기 전에 그 안에 있는 그룹을 일정에 대 한 모든 참조를 해제 해야 합니다.  
  
##  <a name="a-namegetnumberofvirtualprocessorsa-getnumberofvirtualprocessors"></a><a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러에 대 한 가상 프로세서의 현재 수입니다.  
  
##  <a name="a-namegetpolicya-getpolicy"></a><a name="getpolicy"></a>정책 가져오기 

 생성 된 스케줄러 정책의 복사본을 반환 합니다.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 생성 된 스케줄러 정책의 복사본입니다.  
  
##  <a name="a-nameida-id"></a><a name="id"></a>Id 

 스케줄러에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러에 대 한 고유 식별자입니다.  
  
##  <a name="a-nameisavailablelocationa-isavailablelocation"></a><a name="isavailablelocation"></a>IsAvailableLocation 

 지정된 된 위치를 스케줄러에서 사용할 수 있는지 여부를 결정 합니다.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 에 대 한 스케줄러를 쿼리 하는 위치에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치 여부를 나타내는 값은 `_Placement` 인수는 스케줄러에서 사용할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 반환 값은 지정된 위치를 사용할 수 있는지 여부의 순간 샘플링입니다. 여러 스케줄러가 있으면 동적 자원 관리에서 어느 시점에 스케줄러의 리소스를 추가하거나 제거할 수 있습니다. 이 경우 지정된 위치의 가용성이 변경될 수 있습니다.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>참조 

 스케줄러 참조 횟수를 증가 시킵니다.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>반환 값  
 새로 증가 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 이 구성에 대 한 스케줄러의 수명을 관리 하려면 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가&0;이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.  
  
 메서드를 발생 시킵니다는 [improper_scheduler_reference](improper-scheduler-reference-class.md) 참조 횟수를 호출 하기 전에 경우 예외는 `Reference` 메서드가&0;이 고 스케줄러에서 소유 하지 않은 컨텍스트를 호출 합니다.  
  
##  <a name="a-nameregistershutdowneventa-registershutdownevent"></a><a name="registershutdownevent"></a>RegisterShutdownEvent 

 Windows 이벤트 핸들 변수에 전달은 `_Event` 매개 변수는 스케줄러가 종료 되 고 소멸 때 신호를 보낼 수 있습니다. 이벤트는 동시에 스케줄러에 예약한 하는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Event`  
 스케줄러를 종료 하 고 자체를 삭제 하는 경우 런타임에서 신호는 Windows 이벤트 개체에 대 한 핸들입니다.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>릴리스 

 스케줄러 참조 횟수를 감소시킵니다.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새로 감소 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 이 구성에 대 한 스케줄러의 수명을 관리 하려면 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가&0;이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.  
  
##  <a name="a-nameresetdefaultschedulerpolicya-resetdefaultschedulerpolicy"></a><a name="resetdefaultschedulerpolicy"></a>ResetDefaultSchedulerPolicy 

 기본 스케줄러 정책을 런타임 기본값으로 다시 설정 합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정을 사용 합니다.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>주의  
 기본 스케줄러를 프로세스 내에 존재 하는 동안이 메서드를 호출할 수 있습니다. 기존의 기본 스케줄러의 정책에 따라 영향을 주지 않습니다. 그러나, 기본 스케줄러를 종료를 나중에 만들 새 기본 된 경우 새로운 스케줄러 런타임 기본 정책 설정을 사용 합니다.  
  
##  <a name="a-namectora-scheduler"></a><a name="ctor"></a>스케줄러 

 개체는 `Scheduler` 팩터리 메서드를 사용 하 여 만든 클래스 수 또는 암시적으로 합니다.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>주의  
 프로세스의 기본 스케줄러는 호출 컨텍스트에 연결 된 스케줄러를 필요로 하는 런타임 함수를 많이 이용할 때 암시적으로 생성 됩니다. 내에서 메서드는 `CurrentScheduler` 클래스 및 PPL 및 에이전트 레이어의 기능 암시적 첨부 파일을 일반적으로 수행 합니다.  
  
 스케줄러를 통해 명시적으로 만들 수도 있습니다는 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 메서드.  
  
##  <a name="a-namedtora-scheduler"></a><a name="dtor"></a>~ 스케줄러 

 개체는 `Scheduler` 클래스는 모든 외부 참조가 사라질 때 암시적으로 소멸 됩니다.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

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
 작업의 본문에 매개 변수로 전달 되는 데이터에는 void 포인터입니다.  
  
 `_Placement`  
 간단한 작업이 실행될 수 있는 위치에 대한 참조입니다.  
  
##  <a name="a-namesetdefaultschedulerpolicya-setdefaultschedulerpolicy"></a><a name="setdefaultschedulerpolicy"></a>SetDefaultSchedulerPolicy 

 사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 기본 스케줄러가 프로세스 내에 존재 하는 경우에이 메서드를 호출할 수 있습니다. 다음 유효한 호출 될 때까지 적용 됩니다 기본 정책은 설정 된 후의 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Policy`  
 기본 스케줄러 정책으로 설정 하는 정책입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `SetDefaultSchedulerPolicy` 기본 스케줄러를 프로세스 내에서 이미 있는 경우 메서드가 호출 되 면 런타임에서 발생 시킵니다는 [default_scheduler_exists](default-scheduler-exists-class.md) 예외입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [Scheduler 클래스](scheduler-class.md)   
 [PolicyElementKey 열거형](concurrency-namespace-enums.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




