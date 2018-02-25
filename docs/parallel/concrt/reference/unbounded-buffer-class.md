---
title: "unbounded_buffer 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecddf2327e3b2e29dd3c9a857227c03d9e880ef4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
`unbounded_buffer` 메시징 블록은 메시지를 개수에 제한 없이 저장할 수 있는, 순서가 지정된 다중 대상 다중 소스 `propagator_block`입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Type`  
 저장 하 고 버퍼에 의해 전파 메시지의 페이로드 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[unbounded_buffer](#ctor)|오버로드됨. 생성 된 `unbounded_buffer` 메시징 블록입니다.|  
|[~unbounded_buffer Destructor](#dtor)|소멸 된 `unbounded_buffer` 메시징 블록입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[dequeue](#dequeue)|항목을 제거는 `unbounded_buffer` 메시징 블록입니다.|  
|[enqueue](#enqueue)|항목을 추가 `unbounded_buffer` 메시징 블록입니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `unbounded_buffer` 호출자에 게 소유권을 전송 하는 메시징 블록입니다.|  
|[consume_message](#consume_message)|이전에 제공한 메시지 소비는 `unbounded_buffer` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.|  
|[link_target_notification](#link_target_notification)|이 새 대상 연결을 알리는 콜백입니다 `unbounded_buffer` 메시징 블록입니다.|  
|[process_input_messages](#process_input_messages)|위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공을 시도 합니다.|  
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 이 호출 하는 `propagate` 소스 블록에서 호출 될 경우이 메서드.|  
|[propagate_output_messages](#propagate_output_messages)|위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공을 시도 합니다. (재정의 [source_block:: propagate_output_messages](source-block-class.md#propagate_output_messages).)|  
|[release_message](#release_message)|이전의 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|이 이전에 제공 메시지를 예약 `unbounded_buffer` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 이 호출 하는 `send` 소스 블록에서 호출 될 경우이 메서드.|  
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. (재정의 [itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  

 자세한 내용은 참조 [비동기 메시지 블록](../asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="accept_message"></a> accept_message 

 이 제공 된 메시지를 수락 `unbounded_buffer` 호출자에 게 소유권을 전송 하는 메시징 블록입니다.  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
##  <a name="consume_message"></a> consume_message 

 이전에 제공한 메시지 소비는 `unbounded_buffer` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 사용 되는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>설명  
 비슷한 `accept`를를 호출 하 여 항상 선행 `reserve`합니다.  
  
##  <a name="dequeue"></a> 큐에서 제거 

 항목을 제거는 `unbounded_buffer` 메시징 블록입니다.  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>반환 값  
 제거 하는 메시지의 페이로드에 `unbounded_buffer`합니다.  
  
##  <a name="enqueue"></a> 큐에 넣기 

 항목을 추가 `unbounded_buffer` 메시징 블록입니다.  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Item`  
 추가할 항목입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 항목 수락 되 면 `false` 그렇지 않은 경우.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 이 새 대상 연결을 알리는 콜백입니다 `unbounded_buffer` 메시징 블록입니다.  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 새로 연결 된 대상에 대 한 포인터입니다.  
  
##  <a name="propagate_message"></a> propagate_message 

 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 이 호출 하는 `propagate` 소스 블록에서 호출 될 경우이 메서드.  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md#message_status) 메시지로 하기로 하는 대상의 표시 합니다.  
  
##  <a name="propagate_output_messages"></a> propagate_output_messages 

 위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공을 시도 합니다.  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>설명  
 이미 다른 메시지가에서 앞 적용 되었는지는 `unbounded_buffer`, 연결 된 대상의 전파는 이전 메시지가 수락 되거나 사용 될 때까지 발생 하지 것입니다. 성공적으로 연결 된 하는 대상이 첫 번째 `accept` 또는 `consume` 메시지 소유권 및 다른 대상이 없습니다. 메시지를 가져올 수 있습니다.  
  
##  <a name="process_input_messages"></a> process_input_messages 

 위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공을 시도 합니다.  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
  
##  <a name="release_message"></a> release_message 

 이전의 메시지 예약을 해제합니다.  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
##  <a name="reserve_message"></a> reserve_message 

 이 이전에 제공 메시지를 예약 `unbounded_buffer` 메시징 블록입니다.  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
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

 메시지를 동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 이 호출 하는 `send` 소스 블록에서 호출 될 경우이 메서드.  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md#message_status) 메시지로 하기로 하는 대상의 표시 합니다.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 `supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>반환 값  
 블록은 제공된 메시지를 연기하지 않기 때문에 `true`입니다.  
  
##  <a name="ctor"></a> unbounded_buffer 

 생성 된 `unbounded_buffer` 메시징 블록입니다.  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Filter`  
 제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수  
  
 `_PScheduler`  
 `Scheduler` 의 전파에 대 한 작업이 있는 개체는 `unbounded_buffer` 메시징 블록 예약 됩니다.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` 의 전파에 대 한 작업이 있는 개체는 `unbounded_buffer` 메시징 블록 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>설명  
 런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.  
  
 형식 `filter_method` 시그니처가 있는 함수는 `bool (_Type const &)` 이 호출 되는 `unbounded_buffer` 제공된 된 메시지를 수락 해야 하는지 여부를 결정 하는 메시징 블록입니다.  
  
##  <a name="dtor"></a> ~unbounded_buffer 

 소멸 된 `unbounded_buffer` 메시징 블록입니다.  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [overwrite_buffer 클래스](overwrite-buffer-class.md)   
 [single_assignment 클래스](single-assignment-class.md)


