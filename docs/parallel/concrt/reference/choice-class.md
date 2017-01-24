---
title: "choice 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::choice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "choice 클래스"
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# choice 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`choice` 메시징 블록은 소스 집합과의 제어 흐름 상호 작용을 나타내는 다중 소스 단일 대상 블록입니다. 선택한 블록은 여러 소스 중 하나가 메시지를 생성할 때까지 대기하고 메시지를 생성한 소스의 인덱스를 전파합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 A `tuple`-기반 입력 소스의 페이로드를 나타내는 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[choice:: choice 생성자](#choice__choice_constructor)|오버로드됨. `choice` 메시징 블록을 생성합니다.|  
|[choice:: ~ choice 소멸자](#choice___dtorchoice_destructor)|소멸은 `choice` 메시징 블록입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[choice:: accept 메서드](#choice__accept_method)|이 제공 된 메시지를 수락 `choice` 블록을 호출자에 게 소유권을 전송 합니다.|  
|[choice:: acquire_ref 메서드](#choice__acquire_ref_method)|이 대 한 참조 횟수를 획득 `choice` 삭제를 방지 하기 위해 메시징 블록입니다.|  
|[choice:: consume 메서드](#choice__consume_method)|이전에 제공한이 메시지를 생성 `choice` 메시징 블록을 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 되어 있습니다.|  
|[choice:: has_value 메서드](#choice__has_value_method)|확인 여부를이 `choice` 아직 메시징 블록 값으로 초기화 했습니다.|  
|[choice:: index 메서드](#choice__index_method)|에 대 한 인덱스를 반환 된 `tuple` 하 여 선택한 요소를 나타내는 `choice` 메시징 블록입니다.|  
|[choice:: link_target 메서드](#choice__link_target_method)|이 대상 블록을 연결 `choice` 메시징 블록입니다.|  
|[choice:: release 메서드](#choice__release_method)|이전의 성공적인 메시지 예약을 해제합니다.|  
|[choice:: release_ref 메서드](#choice__release_ref_method)|이 대 한 참조 횟수를 해제 `choice` 메시징 블록입니다.|  
|[choice:: reserve 메서드](#choice__reserve_method)|이전에 제공한이 메시지를 예약 `choice` 메시징 블록입니다.|  
|[choice:: unlink_target 메서드](#choice__unlink_target_method)|이 대상 블록을 연결 해제 `choice` 메시징 블록입니다.|  
|[choice:: unlink_targets 메서드](#choice__unlink_targets_method)|이 모든 대상의 연결을 해제 `choice` 메시징 블록입니다. (재정의 [Isource:: Unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
|[choice:: value 메서드](#choice__value_method)|인덱스를 포함 하 여 선택한 메시지를 가져옵니다는 `choice` 메시징 블록입니다.|  
  
## <a name="remarks"></a>설명  
 선택한 블록을 사용 하면 들어오는 메시지 중 하나에 사용 됩니다.  
  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namechoiceacceptmethoda-choiceaccept-method"></a><a name="choice__accept_method"></a>  choice:: accept 메서드  
 이 제공 된 메시지를 수락 `choice` 블록을 호출자에 게 소유권을 전송 합니다.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
  `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `accept` 메서드.  
  
### <a name="return-value"></a>반환 값  
 호출자는 이제 소유권을 가진 메시지에 대 한 포인터입니다.  
  
##  <a name="a-namechoiceacquirerefmethoda-choiceacquireref-method"></a><a name="choice__acquire_ref_method"></a>  choice:: acquire_ref 메서드  
 이 대 한 참조 횟수를 획득 `choice` 삭제를 방지 하기 위해 메시징 블록입니다.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 한 `ITarget` 동안이 소스에 연결 중인 개체는 `link_target` 메서드.  
  
##  <a name="a-namechoicechoiceconstructora-choicechoice-constructor"></a><a name="choice__choice_constructor"></a>  choice:: choice 생성자  
 `choice` 메시징 블록을 생성합니다.  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Tuple`  
 선택을 위한 소스의 `tuple` 입니다.  
  
 `_PScheduler`  
 `Scheduler` 메시징 블록의 전파 작업이 예약되는 `choice` 개체입니다.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `choice` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
 `_Choice`  
 복사할 `choice` 메시징 블록입니다. 원래 개체는 고아로 표시되어 생성자가 이동하도록 합니다.  
  
### <a name="remarks"></a>설명  
 런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.  
  
 잠금이 있는 경우 이동 생성은 수행되지 않습니다. 즉, 이동하는 중에 간단한 작업이 실행되고 있지 않은지 확인할 책임은 사용자에게 있습니다. 그러지 않으면 수많은 레이스가 발생하여 예외가 발생하거나 일관성 없는 상태가 될 수 있습니다.  
  
##  <a name="a-namechoicedtorchoicedestructora-choicechoice-destructor"></a><a name="choice___dtorchoice_destructor"></a>  choice:: ~ choice 소멸자  
 소멸은 `choice` 메시징 블록입니다.  
  
```  
~choice();
```  
  
##  <a name="a-namechoiceconsumemethoda-choiceconsume-method"></a><a name="choice__consume_method"></a>  choice:: consume 메서드  
 이전에 제공한이 메시지를 생성 `choice` 메시징 블록을 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 되어 있습니다.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
  `runtime_object_identity` 예약의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `consume` 메서드.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>설명  
  `consume` 메서드는 `accept`, 를 호출 하 여 앞에 항상 있어야 하지만 `reserve` 반환 `true`.  
  
##  <a name="a-namechoicehasvaluemethoda-choicehasvalue-method"></a><a name="choice__has_value_method"></a>  choice:: has_value 메서드  
 확인 여부를이 `choice` 아직 메시징 블록 값으로 초기화 했습니다.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 블록은 값을 받은 경우 `false` 그렇지 않은 경우.  
  
##  <a name="a-namechoiceindexmethoda-choiceindex-method"></a><a name="choice__index_method"></a>  choice:: index 메서드  
 에 대 한 인덱스를 반환 된 `tuple` 하 여 선택한 요소를 나타내는 `choice` 메시징 블록입니다.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>반환 값  
 메시지 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 메시지 페이로드를 추출할 수는 `get` 메서드.  
  
##  <a name="a-namechoicelinktargetmethoda-choicelinktarget-method"></a><a name="choice__link_target_method"></a>  choice:: link_target 메서드  
 이 대상 블록을 연결 `choice` 메시징 블록입니다.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 에 대 한 포인터는 `ITarget` 이에 연결 하는 블록 `choice` 메시징 블록입니다.  
  
##  <a name="a-namechoicereleasemethoda-choicerelease-method"></a><a name="choice__release_method"></a>  choice:: release 메서드  
 이전의 성공적인 메시지 예약을 해제합니다.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
  `runtime_object_identity` 의 `message` 해제 하 고 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `release` 메서드.  
  
##  <a name="a-namechoicereleaserefmethoda-choicereleaseref-method"></a><a name="choice__release_ref_method"></a>  choice:: release_ref 메서드  
 이 대 한 참조 횟수를 해제 `choice` 메시징 블록입니다.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 한 `ITarget` 이 원본의 연결이 해제 되는 개체입니다. 소스 블록은 대상 블록에 대 한 예약 된 리소스를 해제할 수 있습니다.  
  
##  <a name="a-namechoicereservemethoda-choicereserve-method"></a><a name="choice__reserve_method"></a>  choice:: reserve 메서드  
 이전에 제공한이 메시지를 예약 `choice` 메시징 블록입니다.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
  `runtime_object_identity` 의 `message` 예약 되는 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `reserve` 메서드.  
  
### <a name="return-value"></a>반환 값  
 `true` 메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 호출한 후 `reserve`, 를 호출 해야 성공 하면 `consume` 또는 `release` 을 얻거나 각각 메시지, 소유권을 포기 하기 위해.  
  
##  <a name="a-namechoiceunlinktargetmethoda-choiceunlinktarget-method"></a><a name="choice__unlink_target_method"></a>  choice:: unlink_target 메서드  
 이 대상 블록을 연결 해제 `choice` 메시징 블록입니다.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 에 대 한 포인터는 `ITarget` 블록에서이 연결을 끊을 `choice` 메시징 블록입니다.  
  
##  <a name="a-namechoiceunlinktargetsmethoda-choiceunlinktargets-method"></a><a name="choice__unlink_targets_method"></a>  choice:: unlink_targets 메서드  
 이 모든 대상의 연결을 해제 `choice` 메시징 블록입니다.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>설명  
 때문에 소멸자에서 호출 하지 않아도이 메서드는 내부에 대 한 소멸자 `single_assignment` 블록을 제대로 연결 해제 합니다.  
  
##  <a name="a-namechoicevaluemethoda-choicevalue-method"></a><a name="choice__value_method"></a>  choice:: value 메서드  
 인덱스를 포함 하 여 선택한 메시지를 가져옵니다는 `choice` 메시징 블록입니다.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Payload_type`  
 메시지 페이로드 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지의 페이로드입니다.  
  
### <a name="remarks"></a>설명  
 `choice` 메시징 블록은 페이로드 형식이 서로 다른 입력을 사용할 수 있기 때문에 검색 시 페이로드의 형식을 지정해야 합니다. 결과에 따라 형식을 확인할 수는 `index` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 네임 스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [join 클래스](../../../parallel/concrt/reference/join-class.md)   
 [single_assignment 클래스](../../../parallel/concrt/reference/single-assignment-class.md)
