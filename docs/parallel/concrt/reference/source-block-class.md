---
title: "source_block 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
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
ms.openlocfilehash: b31f02559da7e4396926ce7611a6907c32693121
ms.lasthandoff: 03/17/2017

---
# <a name="sourceblock-class"></a>source_block 클래스
`source_block` 클래스는 소스 전용 블록에 대한 추상 기본 클래스입니다. 이 클래스는 기본 링크 관리 기능 및 일반적인 오류 검사를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_TargetLinkRegistry`  
 대상 링크를 저장에 사용할 레지스트리를 링크 합니다.  
  
 `_MessageProcessorType`  
 메시지 처리에 대 한 프로세서 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`target_iterator`|연결된 된 대상을 탐색 반복기입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[source_block](#ctor)|`source_block` 개체를 생성합니다.|  
|[~ source_block 소멸자](#dtor)|소멸은 `source_block` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[수락](#accept)|이 제공 된 메시지를 수락 `source_block` 개체를 호출자에 게 소유권을 전송 합니다.|  
|[acquire_ref](#acquire_ref)|이 대 한 참조 횟수를 획득 `source_block` 삭제를 방지 하기 위해 개체입니다.|  
|[사용](#consume)|이전에 제공한이 메시지를 생성 `source_block` 개체를 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 되어 있습니다.|  
|[link_target](#link_target)|이 대상 블록을 연결 `source_block` 개체입니다.|  
|[release](#release)|이전의 성공적인 메시지 예약을 해제합니다.|  
|[release_ref](#release_ref)|이 대 한 참조 횟수를 해제 `source_block` 개체입니다.|  
|[reserve](#reserve)|이전에 제공한이 메시지를 예약 `source_block` 개체입니다.|  
|[unlink_target](#unlink_target)|이 대상 블록을 연결 해제 `source_block` 개체입니다.|  
|[unlink_targets](#unlink_targets)|이 모든 대상 블록의 연결을 해제 `source_block` 개체입니다. (재정의 [isource:: Unlink_targets](isource-class.md#unlink_targets).)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept_message](#accept_message)|파생된 클래스에서 재정의 되 면 소스에서 제공된 된 메시지를 수락 합니다. 메시지 블록의 유효성을 검사 하려면이 메서드를 재정의 하는 `_MsgId` 고 메시지를 반환 합니다.|  
|[async_send](#async_send)|비동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 전파 작업을 시작|  
|[consume_message](#consume_message)|파생된 클래스에서 재정의 되 면 이전에 예약 된 메시지를 생성 합니다.|  
|[enable_batched_processing](#enable_batched_processing)|이 블록에 대한 일괄 처리를 할 수 있도록 합니다.|  
|[initialize_source](#initialize_source)|초기화는 `message_propagator` 이 `source_block`합니다.|  
|[link_target_notification](#link_target_notification)|새 대상에 연결 되어 있는 알리는 콜백입니다 `source_block` 개체입니다.|  
|[process_input_messages](#process_input_messages)|입력된 메시지를 처리합니다. source_block에서 파생되는 전파자 블록에만 유용합니다.|  
|[propagate_output_messages](#propagate_output_messages)|메시지를 대상으로 전파합니다.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|파생된 클래스에서 재정의 되 면 연결 된 대상 중 일부 또는 모두 지정된 된 메시지를 전파 합니다. 이것이 메시지 블록에 대 한 주 전파 루틴입니다.|  
|[release_message](#release_message)|파생된 클래스에서 재정의 되 면 이전 메시지 예약을 해제 합니다.|  
|[remove_targets](#remove_targets)|이 소스 블록에 대 한 모든 대상 링크를 제거합니다. 이 소멸자에서 호출 되어야 합니다.|  
|[reserve_message](#reserve_message)|파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 예약 `source_block` 개체입니다.|  
|[resume_propagation](#resume_propagation)|파생된 클래스에서 재정의 되 면 전파 예약이 해제 된 후 다시 시작 합니다.|  
|[sync_send](#sync_send)|동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 전파 작업을 시작 합니다.|  
|[unlink_target_notification](#unlink_target_notification)|대상에서 연결 되었음을 알리는 콜백입니다 `source_block` 개체입니다.|  
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|모든 비동기 전파가 완료 될 때까지 기다립니다. 이 전파 자가 특정 스핀 대기 모든 비동기 전파가 블록을 삭제 하기 전에 완료 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 됩니다.|  
  
## <a name="remarks"></a>주의  
 메시지 블록 연결 관리와이 클래스에서 제공 하는 동기화를 활용 하기 위해이 블록에서 파생 되어야 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="accept"></a>수락 

 이 제공 된 메시지를 수락 `source_block` 개체를 호출자에 게 소유권을 전송 합니다.  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `accept` 메서드.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
 `accept` 메서드는 대상에 의해이 메시지를 제공 하는 동안 `ISource` 블록입니다. 메시지 포인터가 반환에 전달 된 것과에서 다를 수 있습니다는 `propagate` 의 메서드는 `ITarget` 이 원본 메시지의 복사본을 확인 하기로 결정 하는 경우 차단 합니다.  
  
##  <a name="accept_message"></a>accept_message 

 파생된 클래스에서 재정의 되 면 소스에서 제공된 된 메시지를 수락 합니다. 메시지 블록의 유효성을 검사 하려면이 메서드를 재정의 하는 `_MsgId` 고 메시지를 반환 합니다.  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 런타임 개체 id는 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 호출자는 이제 소유권을 가진 메시지에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 소유권을 전송 하려면 원래 메시지 포인터를 반환 합니다. 소유권을 유지 하려면 메시지 페이로드의 복사본 해야 만들고 반환 해야 합니다.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 이 대 한 참조 횟수를 획득 `source_block` 삭제를 방지 하기 위해 개체입니다.  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 한 `ITarget` 동안이 소스에 연결 중인 개체의 `link_target` 메서드.  
  
##  <a name="async_send"></a>async_send 

 비동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 전파 작업을 시작  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 에 대 한 포인터는 `message` 비동기적으로 보낼 개체입니다.  
  
##  <a name="consume"></a>사용 

 이전에 제공한이 메시지를 생성 `source_block` 개체를 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 되어 있습니다.  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 예약의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `consume` 메서드.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
 메서드에서 throw 한 [bad_target](bad-target-class.md) 예외 경우 매개 변수 `_PTarget` 호출 하는 대상을 나타내지 않는 `reserve`합니다.  
  
 `consume` 메서드는 `accept`를 호출 하 여 앞에 항상 있어야 하지만 `reserve` 반환 `true`.  
  
##  <a name="consume_message"></a>consume_message 

 파생된 클래스에서 재정의 되 면 이전에 예약 된 메시지를 생성 합니다.  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 소비 되 고 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 호출자는 이제 소유권을 가진 메시지에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.  
  
##  <a name="enable_batched_processing"></a>enable_batched_processing 

 이 블록에 대한 일괄 처리를 할 수 있도록 합니다.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_source"></a>initialize_source 

 초기화는 `message_propagator` 이 `source_block`합니다.  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PScheduler`  
 작업을 예약 하는 데 사용할 스케줄러입니다.  
  
 `_PScheduleGroup`  
 작업을 예약 하는 데 사용할 일정 그룹입니다.  
  
##  <a name="link_target"></a>link_target 

 이 대상 블록을 연결 `source_block` 개체입니다.  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 에 대 한 포인터는 `ITarget` 이에 연결 하는 블록 `source_block` 개체입니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
##  <a name="link_target_notification"></a>link_target_notification 

 새 대상에 연결 되어 있는 알리는 콜백입니다 `source_block` 개체입니다.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="process_input_messages"></a>process_input_messages 

 입력된 메시지를 처리합니다. source_block에서 파생되는 전파자 블록에만 유용합니다.  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
  
##  <a name="propagate_output_messages"></a>propagate_output_messages 

 메시지를 대상으로 전파합니다.  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 파생된 클래스에서 재정의 되 면 연결 된 대상 중 일부 또는 모두 지정된 된 메시지를 전파 합니다. 이것이 메시지 블록에 대 한 주 전파 루틴입니다.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 전파 되는 메시지에 대 한 포인터입니다.  
  
##  <a name="release"></a>릴리스 

 이전의 성공적인 메시지 예약을 해제합니다.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 예약의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `release` 메서드.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
 메서드에서 throw 한 [bad_target](bad-target-class.md) 예외 경우 매개 변수 `_PTarget` 호출 하는 대상을 나타내지 않는 `reserve`합니다.  
  
##  <a name="release_message"></a>release_message 

 파생된 클래스에서 재정의 되 면 이전 메시지 예약을 해제 합니다.  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
##  <a name="release_ref"></a>release_ref 

 이 대 한 참조 횟수를 해제 `source_block` 개체입니다.  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 한 `ITarget` 이 원본의 연결이 해제 되는 개체입니다. 소스 블록은 대상 블록에 대 한 예약 된 리소스를 해제할 수 있습니다.  
  
##  <a name="remove_targets"></a>remove_targets 

 이 소스 블록에 대 한 모든 대상 링크를 제거합니다. 이 소멸자에서 호출 되어야 합니다.  
  
```
void remove_targets();
```  
  
##  <a name="reserve"></a>예약 

 이전에 제공한이 메시지를 예약 `source_block` 개체입니다.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `reserve` 메서드.  
  
### <a name="return-value"></a>반환 값  
 `true`메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
 호출한 후 `reserve`를 호출 해야 성공 하면 `consume` 또는 `release` 을 얻거나 각각 메시지, 소유권을 포기 하기 위해.  
  
##  <a name="reserve_message"></a>reserve_message 

 파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 예약 `source_block` 개체입니다.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 예약 되는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 후 `reserve` 반환 하는 경우 라고 `true`를 `consume` 또는 `release` 얻거나 메시지의 소유권을 해제 하려면를 호출 해야 합니다.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 파생된 클래스에서 재정의 되 면 전파 예약이 해제 된 후 다시 시작 합니다.  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="ctor"></a>source_block 

 `source_block` 개체를 생성합니다.  
  
```
source_block();
```  
  
##  <a name="dtor"></a>~ source_block 

 소멸은 `source_block` 개체입니다.  
  
```
virtual ~source_block();
```  
  
##  <a name="sync_send"></a>sync_send 

 동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 전파 작업을 시작 합니다.  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 에 대 한 포인터는 `message` 동기적으로 보낼 개체입니다.  
  
##  <a name="unlink_target"></a>unlink_target 

 이 대상 블록을 연결 해제 `source_block` 개체입니다.  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 에 대 한 포인터는 `ITarget` 블록에서이 연결을 끊을 `source_block` 개체입니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_PTarget` 는 `NULL`합니다.  
  
##  <a name="unlink_target_notification"></a>unlink_target_notification 

 대상에서 연결 되었음을 알리는 콜백입니다 `source_block` 개체입니다.  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 `ITarget` 연결 되지 않은 블록입니다.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 이 모든 대상 블록의 연결을 해제 `source_block` 개체입니다.  
  
```
virtual void unlink_targets();
```  
  
##  <a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends 

 모든 비동기 전파가 완료 될 때까지 기다립니다. 이 전파 자가 특정 스핀 대기 모든 비동기 전파가 블록을 삭제 하기 전에 완료 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 됩니다.  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ISource 클래스](isource-class.md)

