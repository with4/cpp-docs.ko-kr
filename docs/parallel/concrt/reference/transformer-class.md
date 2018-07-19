---
title: transformer 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- transformer
- AGENTS/concurrency::transformer
- AGENTS/concurrency::transformer::transformer
- AGENTS/concurrency::transformer::accept_message
- AGENTS/concurrency::transformer::consume_message
- AGENTS/concurrency::transformer::link_target_notification
- AGENTS/concurrency::transformer::propagate_message
- AGENTS/concurrency::transformer::propagate_to_any_targets
- AGENTS/concurrency::transformer::release_message
- AGENTS/concurrency::transformer::reserve_message
- AGENTS/concurrency::transformer::resume_propagation
- AGENTS/concurrency::transformer::send_message
- AGENTS/concurrency::transformer::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9ea43e1d3f6f369b93e92e91fa3606cf7d6af5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693782"
---
# <a name="transformer-class"></a>transformer 클래스
`transformer` 메시징 블록은 한 형식의 메시지를 수락하고 다른 형식의 메시지를 개수에 제한 없이 저장할 수 있는 순서가 지정된 단일 대상 다중 소스 `propagator_block`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```   
  
#### <a name="parameters"></a>매개 변수  
 `_Input`  
 버퍼에서 허용 하는 메시지의 페이로드 유형입니다.  
  
 `_Output`  
 저장 하 고 버퍼에 의해 전파 메시지의 페이로드 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[transformer](#ctor)|오버로드됨. 생성 된 `transformer` 메시징 블록입니다.|  
|[~ transformer 소멸자](#dtor)|소멸 된 `transformer` 메시징 블록입니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `transformer` 호출자에 게 소유권을 전송 하는 메시징 블록입니다.|  
|[consume_message](#consume_message)|이전에 제공한 메시지 소비는 `transformer` , 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.|  
|[link_target_notification](#link_target_notification)|이 새 대상 연결을 알리는 콜백입니다 `transformer` 메시징 블록입니다.|  
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `transformer` 메시징 블록입니다. 이 호출 하는 `propagate` 소스 블록에서 호출 될 경우이 메서드.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|입력 메시지에 대해 변형기 함수를 실행합니다.|  
|[release_message](#release_message)|이전의 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|이 이전에 제공 메시지를 예약 `transformer` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `transformer` 메시징 블록입니다. 이 호출 하는 `send` 소스 블록에서 호출 될 경우이 메서드.|  
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. (재정의 [itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `transformer`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="accept_message"></a> accept_message 

 이 제공 된 메시지를 수락 `transformer` 호출자에 게 소유권을 전송 하는 메시징 블록입니다.  
  
```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
##  <a name="consume_message"></a> consume_message 

 이전에 제공한 메시지 소비는 `transformer` , 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.  
  
```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 사용 되는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>설명  
 비슷한 `accept`를를 호출 하 여 항상 선행 `reserve`합니다.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 이 새 대상 연결을 알리는 콜백입니다 `transformer` 메시징 블록입니다.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```  
  
##  <a name="propagate_message"></a> propagate_message 

 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `transformer` 메시징 블록입니다. 이 호출 하는 `propagate` 소스 블록에서 호출 될 경우이 메서드.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지로 하기로 하는 대상의 표시 합니다.  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 입력 메시지에 대해 변형기 함수를 실행합니다.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```  
  
##  <a name="release_message"></a> release_message 

 이전의 메시지 예약을 해제합니다.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
##  <a name="reserve_message"></a> reserve_message 

 이 이전에 제공 메시지를 예약 `transformer` 메시징 블록입니다.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 예약 되 고 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 후 `reserve` 반환 하는 경우 라고 `true`, 어느 `consume` 또는 `release` 호출을 얻거나 메시지의 소유권을 해제 해야 합니다.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 예약을 해제 된 후에 전파를 다시 시작 합니다.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="send_message"></a> send_message 

 메시지를 동기적으로 전달 된 `ISource` 이 블록 `transformer` 메시징 블록입니다. 이 호출 하는 `send` 소스 블록에서 호출 될 경우이 메서드.  
  
```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지로 하기로 하는 대상의 표시 합니다.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 `supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>반환 값  
 블록은 제공된 메시지를 연기하지 않기 때문에 `true`입니다.  
  
##  <a name="ctor"></a> transformer 

 생성 된 `transformer` 메시징 블록입니다.  
  
```
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Func`  
 수락 된 각 메시지에 대 한 호출 되는 함수입니다.  
  
 `_PTarget`  
 변환기를 사용 하 여 링크 대상 블록에 대 한 포인터입니다.  
  
 `_Filter`  
 제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수  
  
 `_PScheduler`  
 `Scheduler` 의 전파에 대 한 작업이 있는 개체는 `transformer` 메시징 블록 예약 됩니다.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` 의 전파에 대 한 작업이 있는 개체는 `transformer` 메시징 블록 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>설명  
 런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.  
  
 형식 `_Transform_method` 시그니처가 있는 함수는 `_Output (_Input const &)` 이 호출 되는 `transformer` 메시징 블록 메시지를 처리 합니다.  
  
 형식 `filter_method` 시그니처가 있는 함수는 `bool (_Input const &)` 이 호출 되는 `transformer` 제공된 된 메시지를 수락 해야 하는지 여부를 결정 하는 메시징 블록입니다.  
  
##  <a name="dtor"></a> ~transformer 

 소멸 된 `transformer` 메시징 블록입니다.  
  
```
~transformer();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [call 클래스](call-class.md)
