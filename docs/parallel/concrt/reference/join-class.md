---
title: "join 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::join
dev_langs:
- C++
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
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
ms.openlocfilehash: b9671e6c9d29fb5f93977fe080e90dd087429460
ms.lasthandoff: 02/24/2017

---
# <a name="join-class"></a>join 클래스
`join` 메시징 블록은 각 소스에서 `T` 형식의 메시지를 결합하는 순서가 지정된 단일 대상 다중 소스 `propagator_block`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```   
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 가입 하 고 블록에 의해 전파 하는 메시지의 페이로드 형식.  
  
 `_Jtype`  
 종류의 `join` 하거나 이것이 블록 `greedy` 또는`non_greedy`  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[생성자를 조인 합니다.](#ctor)|오버로드됨. 생성 된 `join` 메시징 블록입니다.|  
|[~ join 소멸자](#dtor)|소멸은 `join` 블록입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept_message 메서드](#accept_message)|이 제공 된 메시지를 수락 `join` 메시징 블록을 호출자에 게 소유권을 전송 합니다.|  
|[consume_message 메서드](#consume_message)|이전에 제공한 메시지를 생성 된 `join` 메시징 블록 하 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.|  
|[link_target_notification 메서드](#link_target_notification)|새 대상에 연결 되어 있는 알리는 콜백입니다 `join` 메시징 블록입니다.|  
|[propagate_message 메서드](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `join` 메시징 블록입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.|  
|[propagate_to_any_targets 메서드](#propagate_to_any_targets)|전파 될 때 하는 모든 메시지에는 각 소스에서 입력된 메시지를 포함 하는 출력 메시지를 생성 합니다. 이 출력 메시지를 각 대상에 보냅니다.|  
|[release_message 메서드](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message 메서드](#reserve_message)|이전에 제공한이 메시지를 예약 `join` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation 메서드](#resume_propagation)|예약이 해제 된 후 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `join`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 이 제공 된 메시지를 수락 `join` 메시징 블록을 호출자에 게 소유권을 전송 합니다.  
  
```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 이전에 제공한 메시지를 생성 된 `join` 메시징 블록 하 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.  
  
```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 소비 되 고 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>주의  
 비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.  
  
##  <a name="a-namectora-join"></a><a name="ctor"></a>조인 

 생성 된 `join` 메시징 블록입니다.  
  
```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_NumInputs`  
 이 입력 수 `join` 블록 허용 됩니다.  
  
 `_Filter`  
 제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수  
  
 `_PScheduler`  
 `Scheduler` 의 전파에 대 한 작업이 있는 개체는 `join` 메시징 블록 예약 됩니다.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` 의 전파에 대 한 작업이 있는 개체는 `join` 메시징 블록 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>주의  
 런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.  
  
 형식 `filter_method` 시그니처가 있는 함수는 `bool (T const &)` 이 호출 되는 `join` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.  
  
##  <a name="a-namedtora-join"></a><a name="dtor"></a>~ 조인 

 소멸은 `join` 블록입니다.  
  
```
~join();
```  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 새 대상에 연결 되어 있는 알리는 콜백입니다 `join` 메시징 블록입니다.  
  
```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `join` 메시징 블록입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.  
  
```
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 전파 될 때 하는 모든 메시지에는 각 소스에서 입력된 메시지를 포함 하는 출력 메시지를 생성 합니다. 이 출력 메시지를 각 대상에 보냅니다.  
  
```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
```  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 이전 메시지 예약을 해제합니다.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 이전에 제공한이 메시지를 예약 `join` 메시징 블록입니다.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 후 `reserve` 반환 하는 경우 라고 `true`를 `consume` 또는 `release` 얻거나 메시지의 소유권을 해제 하려면를 호출 해야 합니다.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 예약이 해제 된 후 전파를 다시 시작 합니다.  
  
```
virtual void resume_propagation();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [choice 클래스](choice-class.md)   
 [multitype_join 클래스](multitype-join-class.md)

