---
title: "ScheduleGroup 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::ScheduleGroup
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 424b2f53f39bce57c85e44f0df54928acdac399a
ms.lasthandoff: 02/24/2017

---
# <a name="schedulegroup-class"></a>ScheduleGroup 클래스
일정 그룹에 대한 추상화를 나타냅니다. 일정 그룹은 다른 그룹으로 이동하기 전에 동일한 그룹의 다른 작업을 실행하여 시간적으로 또는 동일한 NUMA 노드 또는 실제 소켓에서 동일한 그룹 내의 여러 항목을 실행하여 공간적으로 서로 가깝게 예약하면 도움이 되는 관련된 작업 집합을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[~ ScheduleGroup 소멸자](#dtor)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Id 메서드](#id)|그룹이 속해 있는 스케줄러 내에서 고유한 일정 그룹에 대 한 식별자를 반환 합니다.|  
|[Reference 메서드](#reference)|일정 그룹 참조 횟수를 증가시킵니다.|  
|[Release 메서드](#release)|일정 그룹 참조 횟수를 감소시킵니다.|  
|[ScheduleTask 메서드](#scheduletask)|일정 그룹 내에서 간단한 작업을 예약합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ScheduleGroup`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameida-id"></a><a name="id"></a>Id 

 그룹이 속해 있는 스케줄러 내에서 고유한 일정 그룹에 대 한 식별자를 반환 합니다.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 그룹이 속해 있는 스케줄러 내에서 고유한 일정 그룹에 대 한 식별자입니다.  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>delete 연산자 

 A `ScheduleGroup` 개체가 소멸 내부적으로 런타임에 의해 모든 외부 참조가 릴리스될 때. 개체를 명시적으로 삭제할 수 없습니다.  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>매개 변수  
 `_PObject`  
 삭제할 개체에 대 한 포인터입니다.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>참조 

 일정 그룹 참조 횟수를 증가시킵니다.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새로 증가 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 이 구성에 대 한 일정 그룹의 수명을 관리 하려면 일반적으로 사용 됩니다. 일정 그룹의 참조 횟수가&0;으로, 일정 그룹 런타임에 의해 삭제 됩니다. 일정 그룹 중 하나를 사용 하 여 만든는 [currentscheduler:: Createschedulegroup](currentscheduler-class.md#createschedulegroup) 메서드 또는 [scheduler:: createschedulegroup](scheduler-class.md#createschedulegroup) 메서드 참조 횟수가&1;로 시작 합니다.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>릴리스 

 일정 그룹 참조 횟수를 감소시킵니다.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새로 감소 참조 횟수입니다.  
  
### <a name="remarks"></a>주의  
 이 구성에 대 한 일정 그룹의 수명을 관리 하려면 일반적으로 사용 됩니다. 일정 그룹의 참조 횟수가&0;으로, 일정 그룹 런타임에 의해 삭제 됩니다. `Release` 메서드를 사용하여 배치된 추가 참조와 생성 참조 횟수를 제거하기 위해 `Reference` 메서드를 특정 횟수 만큼 호출한 후에는 더 이상 일정 그룹을 이용할 수 없습니다. 이렇게 하면 정의 되지 않은 동작이 발생 합니다.  
  
 일정 그룹은 특정 스케줄러 인스턴스와 연결 합니다. 스케줄러에 대한 모든 참조는 스케줄러에서 소멸될 수 있기 때문에 스케줄러에 대한 모든 참조가 해제되기 전에 일정 그룹에 대한 모든 참조가 해제되었는지 확인해야 합니다. 그렇지 않으면 결과가 정의 되지 않은 동작을 수행합니다.  
  
##  <a name="a-namedtora-schedulegroup"></a><a name="dtor"></a>~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 일정 그룹 내에서 간단한 작업을 예약합니다.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Proc`  
 간단한 작업의 본문을 수행 하기 위해 실행할 함수에 대 한 포인터입니다.  
  
 `_Data`  
 작업의 본문에 매개 변수로 전달 되는 데이터에는 void 포인터입니다.  
  
### <a name="remarks"></a>주의  
 호출 된 `ScheduleTask` 메서드 작업이 실행 된 후 적절 한 시간에 런타임에 의해 제거 되는 일정 그룹에 대 한 참조 횟수를 암시적으로 배치 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [CurrentScheduler 클래스](currentscheduler-class.md)   
 [Scheduler 클래스](scheduler-class.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




