---
title: "timer 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d6dfdc1b03ac2d15aa575c16cbe86968f565c1c1
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="timer-class"></a>timer 클래스
`timer` 메시징 블록은 지정된 기간이 경과한 후 또는 특정 간격마다 대상에 메시지를 보낼 수 있는 단일 대상 `source_block`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 이 블록의 출력 메시지의 페이로드 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[타이머](#ctor)|오버로드됨. 생성 된 `timer` 지정된 된 간격 후 지정된 된 메시지를 발생 시키는 메시징 블록입니다.|  
|[~ timer 소멸자](#dtor)|삭제는 `timer` 메시징 블록입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[일시 중지](#pause)|중지 된 `timer` 메시징 블록입니다. 반복 되는 경우 `timer` 메시징 블록 것을 다시 시작할 수 이후의 `start()` 를 호출 합니다. -반복 되지 않는 타이머,이 것과 동일한 효과가 `stop` 를 호출 합니다.|  
|[start](#start)|시작 된 `timer` 메시징 블록입니다. 지정된 된 수의 시간 (밀리초)가 호출 되 면 지정된 된 값을 전파 됩니다로 다운스트림는 `message`합니다.|  
|[중지](#stop)|중지 된 `timer` 메시징 블록입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `timer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.|  
|[consume_message](#consume_message)|이전에 제공한 메시지를 생성는 `timer` 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 되어 있습니다.|  
|[link_target_notification](#link_target_notification)|새 대상에 연결 되어 있는 알리는 콜백입니다 `timer` 메시징 블록입니다.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|에 의해 생성 된 메시지를 제공 하도록 시도 `timer` 모든 연결 된 대상에는 블록입니다.|  
|[release_message](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|이전에 제공한이 메시지를 예약 `timer` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|예약이 해제 된 후 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="accept_message"></a>accept_message 

 이 제공 된 메시지를 수락 `timer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
##  <a name="consume_message"></a>consume_message 

 이전에 제공한 메시지를 생성는 `timer` 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 되어 있습니다.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 소비 되 고 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>주의  
 비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.  
  
##  <a name="link_target_notification"></a>link_target_notification 

 새 대상에 연결 되어 있는 알리는 콜백입니다 `timer` 메시징 블록입니다.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 새로 연결 된 대상에 대 한 포인터입니다.  
  
##  <a name="pause"></a>일시 중지 

 중지 된 `timer` 메시징 블록입니다. 반복 되는 경우 `timer` 메시징 블록 것을 다시 시작할 수 이후의 `start()` 를 호출 합니다. -반복 되지 않는 타이머,이 것과 동일한 효과가 `stop` 를 호출 합니다.  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 에 의해 생성 된 메시지를 제공 하도록 시도 `timer` 모든 연결 된 대상에는 블록입니다.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a>release_message 

 이전 메시지 예약을 해제합니다.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
##  <a name="reserve_message"></a>reserve_message 

 이전에 제공한이 메시지를 예약 `timer` 메시징 블록입니다.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 의 `message` 예약 되는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 후 `reserve` 반환 하는 경우 라고 `true`를 `consume` 또는 `release` 얻거나 메시지의 소유권을 해제 하려면를 호출 해야 합니다.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 예약이 해제 된 후 전파를 다시 시작 합니다.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="start"></a>시작 

 시작 된 `timer` 메시징 블록입니다. 지정된 된 수의 시간 (밀리초)가 호출 되 면 지정된 된 값을 전파 됩니다로 다운스트림는 `message`합니다.  
  
```
void start();
```  
  
##  <a name="stop"></a>중지 

 중지 된 `timer` 메시징 블록입니다.  
  
```
void stop();
```  
  
##  <a name="ctor"></a>타이머 

 생성 된 `timer` 지정된 된 간격 후 지정된 된 메시지를 발생 시키는 메시징 블록입니다.  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Ms`  
 지정된 된 메시지를 다운스트림으로 전파에 대 한 시작 하는 호출 후 경과 해야 하는 시간 (밀리초)의 수입니다.  
  
 `value`  
 타이머가 경과 하면 다운스트림 전파할 수 있는 값입니다.  
  
 `_PTarget`  
 타이머 해당 메시지를 전파할 대상입니다.  
  
 `_Repeating`  
 True 이면 타이머가 정기적으로 실행 됩니다 모든 `_Ms` 시간 (밀리초)입니다.  
  
 `_Scheduler`  
 `Scheduler` 의 전파에 대 한 작업이 있는 개체는 `timer` 메시징 블록은 예약 된 예약 됩니다.  
  
 `_ScheduleGroup`  
 `ScheduleGroup` 의 전파에 대 한 작업이 있는 개체는 `timer` 메시징 블록 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>설명  
 런타임에서 지정 하지 않은 경우 기본 스케줄러를 사용 하 여 `_Scheduler` 또는 `_ScheduleGroup` 매개 변수입니다.  
  
##  <a name="dtor"></a>~ 타이머 

 삭제는 `timer` 메시징 블록입니다.  
  
```
~timer();
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)

