---
title: "CurrentScheduler 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CurrentScheduler
- CONCRT/concurrency::CurrentScheduler
- CONCRT/concurrency::CurrentScheduler::Create
- CONCRT/concurrency::CurrentScheduler::CreateScheduleGroup
- CONCRT/concurrency::CurrentScheduler::Detach
- CONCRT/concurrency::CurrentScheduler::Get
- CONCRT/concurrency::CurrentScheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::CurrentScheduler::GetPolicy
- CONCRT/concurrency::CurrentScheduler::Id
- CONCRT/concurrency::CurrentScheduler::IsAvailableLocation
- CONCRT/concurrency::CurrentScheduler::RegisterShutdownEvent
- CONCRT/concurrency::CurrentScheduler::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
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
ms.openlocfilehash: 9536dd28eeb375f3b9e018539cefb338812e340b
ms.lasthandoff: 03/17/2017

---
# <a name="currentscheduler-class"></a>CurrentScheduler 클래스
호출 컨텍스트와 연결된 현재 스케줄러에 대한 추상화를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[만들기](#create)|해당 동작이 설명 하는 새 스케줄러를 만들고는 `_Policy` 매개 변수 호출 컨텍스트에 연결 합니다. 새로 만든된 스케줄러 호출 컨텍스트에 대 한 현재 스케줄러 될 것입니다.|  
|[CreateScheduleGroup](#createschedulegroup)|오버로드됨. 호출 컨텍스트와 연결 된 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.|  
|[Detach](#detach)|호출 컨텍스트를 현재 스케줄러를 분리 하 고 있는 경우 현재 스케줄러로 이전에 연결 된 스케줄러를 복원 합니다. 이 메서드에서 반환 된 후 호출 컨텍스트 중 하나를 사용 하 여 컨텍스트를 이전에 연결 된 스케줄러에서 다음 관리 되는 `CurrentScheduler::Create` 또는 `Scheduler::Attach` 메서드가 있습니다.|  
|[가져오기](#get)|현재 스케줄러 라고도 하는 호출 컨텍스트와 관련 된 스케줄러에 대 한 포인터를 반환 합니다.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|호출 컨텍스트와 연결 된 스케줄러에 대 한 가상 프로세서의 현재 수를 반환 합니다.|  
|[정책 가져오기](#getpolicy)|생성 된 현재 스케줄러 정책의 복사본을 반환 합니다.|  
|[Id](#id)|현재 스케줄러에 대 한 고유 식별자를 반환합니다.|  
|[IsAvailableLocation](#isavailablelocation)|현재 스케줄러에서 지정된 위치를 사용할 수 있는지를 확인합니다.|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows 이벤트 핸들 변수에 전달은 `_ShutdownEvent` 매개 변수를 현재 컨텍스트와 연결 된 스케줄러를 종료 하 고 자체를 삭제 하는 경우 신호를 보낼 수 있습니다. 이벤트는 동시에 스케줄러에 예약한 하는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.|  
|[ScheduleTask](#scheduletask)|오버로드됨. 호출 컨텍스트와 연결 된 스케줄러 내에서 간단한 작업을 예약 합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.|  
  
## <a name="remarks"></a>주의  
 스케줄러가 없는 경우 (참조 [스케줄러](scheduler-class.md)) 내의 많은 메서드 호출 컨텍스트와 연관 된 `CurrentScheduler` 클래스의 프로세스의 기본 스케줄러에에서 발생 합니다. 이러한 호출 중 프로세스의 기본 스케줄러 만들어졌는지 의미할 수도 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CurrentScheduler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="create"></a>만들기 

 해당 동작이 설명 하는 새 스케줄러를 만들고는 `_Policy` 매개 변수 호출 컨텍스트에 연결 합니다. 새로 만든된 스케줄러 호출 컨텍스트에 대 한 현재 스케줄러 될 것입니다.  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Policy`  
 새로 만든된 스케줄러의 동작을 설명 하는 스케줄러 정책.  
  
### <a name="remarks"></a>주의  
 암시적으로 호출 컨텍스트에 대 한 스케줄러의 첨부 파일 스케줄러에 대 한 참조 횟수를 배치합니다.  
  
 으로 스케줄러를 만들고 나면는 `Create` 호출 해야 메서드를는 [currentscheduler:: Detach](#detach) 메서드를 종료 하려면 스케줄러를 허용 하기 위해 나중에 특정 시점입니다.  
  
 이 메서드는 다른 스케줄러에 이미 연결 되어 있는 컨텍스트를, 기존 스케줄러는 이전 스케줄러로 기억 되 고 새로 만든 스케줄러가 현재 스케줄러. 호출 하는 경우는 `CurrentScheduler::Detach` 메서드는 나중에, 이전 스케줄러를 현재 스케줄러로 복원 됩니다.  
  
 이 메서드는 다양 한 예외를 포함 하 여 throw 할 수 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) 및 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)합니다.  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 호출 컨텍스트와 연결 된 스케줄러 내에서 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치에서 실행 하는 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 일정 그룹 내의 작업은 될 수 있는 위치에서 실행에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 일정 그룹에 대 한 포인터입니다. 이 `ScheduleGroup` 개체에 배치 하는 초기 참조 횟수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.  
  
 호출 해야는 [릴리스](schedulegroup-class.md#release) 예약 작업을 완료 하는 일정 그룹에 대 한 메서드. 스케줄러 일정 파기 합니다. 그룹에 큐에 대기 되는 모든 작업 완료 합니다.  
  
 참고가이 스케줄러를 명시적으로 만든 경우 현재 컨텍스트를 분리 하 여 스케줄러에 대 한 참조를 해제 하기 전에 그 안에 있는 그룹을 일정에 대 한 모든 참조를 해제 해야 합니다.  
  
##  <a name="detach"></a>분리 

 호출 컨텍스트를 현재 스케줄러를 분리 하 고 있는 경우 현재 스케줄러로 이전에 연결 된 스케줄러를 복원 합니다. 이 메서드에서 반환 된 후 호출 컨텍스트 중 하나를 사용 하 여 컨텍스트를 이전에 연결 된 스케줄러에서 다음 관리 되는 `CurrentScheduler::Create` 또는 `Scheduler::Attach` 메서드가 있습니다.  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>설명  
 `Detach` 메서드 스케줄러에서 참조 횟수를 암시적으로 제거 합니다.  
  
 스케줄러가 호출 컨텍스트에 연결 된 경우이 메서드를 호출 하면는 [scheduler_not_attached](scheduler-not-attached-class.md) 예외가 throw 됩니다.  
  
 컨텍스트를이 메서드를 호출 되어 내부 이외의 메서드를 사용 하 여 연결 된 컨텍스트 또는 스케줄러를 관리 하는 [scheduler:: attach](scheduler-class.md#attach) 또는 [currentscheduler:: Create](#create) 하면 메서드는 [improper_scheduler_detach](improper-scheduler-detach-class.md) 예외가 throw 됩니다.  
  
##  <a name="get"></a>가져오기 

 현재 스케줄러 라고도 하는 호출 컨텍스트와 관련 된 스케줄러에 대 한 포인터를 반환 합니다.  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>반환 값  
 호출 컨텍스트 (현재 스케줄러)와 관련 된 스케줄러에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다. 에 대 한 추가 참조가 배치 되는 `Scheduler` 이 메서드에서 반환 된 개체입니다.  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 호출 컨텍스트와 연결 된 스케줄러에 대 한 가상 프로세서의 현재 수를 반환 합니다.  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러는 해당 스케줄러;에 대 한 가상 프로세서 수가 현재 호출 컨텍스트와 연관 된 경우 그렇지 않으면 값 `-1`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드 호출 컨텍스트에 이미 스케줄러와 연결 되지 않은 경우 스케줄러에 발생 하지 않습니다.  
  
 이 메서드의 반환 값은 호출 컨텍스트와 연결 된 스케줄러에 대 한 가상 프로세서 수의 순간 샘플링입니다. 이 값은 반환되는 순간 부실 값이 될 수 있습니다.  
  
##  <a name="getpolicy"></a>정책 가져오기 

 생성 된 현재 스케줄러 정책의 복사본을 반환 합니다.  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>반환 값  
 정책의 복사본 생성 된 현재 스케줄러입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.  
  
##  <a name="id"></a>Id 

 현재 스케줄러에 대 한 고유 식별자를 반환합니다.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>반환 값  
 스케줄러 호출 컨텍스트와 해당 스케줄러;에 대 한 고유 식별자와 연결 된 경우 그렇지 않으면 값 `-1`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 호출 컨텍스트에 이미 스케줄러와 연결 되지 않은 경우 스케줄러에 발생 하지 않습니다.  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 현재 스케줄러에서 지정된 위치를 사용할 수 있는지를 확인합니다.  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Placement`  
 현재 스케줄러를 쿼리하는 위치에 대한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 `_Placement` 인수로 지정된 위치를 현재 스케줄러에서 사용할 수 있는지 여부를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 호출 컨텍스트에 이미 스케줄러와 연결 되지 않은 경우 스케줄러에 발생 하지 않습니다.  
  
 반환 값은 지정된 위치를 사용할 수 있는지 여부의 순간 샘플링입니다. 여러 스케줄러가 있으면 동적 자원 관리에서 어느 시점에 스케줄러의 리소스를 추가하거나 제거할 수 있습니다. 이 경우 지정된 위치의 가용성이 변경될 수 있습니다.  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Windows 이벤트 핸들 변수에 전달은 `_ShutdownEvent` 매개 변수를 현재 컨텍스트와 연결 된 스케줄러를 종료 하 고 자체를 삭제 하는 경우 신호를 보낼 수 있습니다. 이벤트는 동시에 스케줄러에 예약한 하는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 `_ShutdownEvent`  
 현재 컨텍스트와 연결 된 스케줄러를 종료 하 고 자체를 삭제 하는 경우 런타임에서 신호는 Windows 이벤트 개체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 스케줄러가 호출 컨텍스트에 연결 된 경우이 메서드를 호출 하면는 [scheduler_not_attached](scheduler-not-attached-class.md) 예외가 throw 됩니다.  
  
##  <a name="scheduletask"></a>ScheduleTask 

 호출 컨텍스트와 연결 된 스케줄러 내에서 간단한 작업을 예약 합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.  
  
```
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Proc`  
 간단한 작업의 본문을 수행 하기 위해 실행할 함수에 대 한 포인터입니다.  
  
 `_Data`  
 작업의 본문에 매개 변수로 전달 되는 데이터에는 void 포인터입니다.  
  
 `_Placement`  
 간단한 작업이 실행될 수 있는 위치에 대한 참조입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [Scheduler 클래스](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




