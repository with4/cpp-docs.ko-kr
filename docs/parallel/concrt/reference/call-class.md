---
title: "클래스를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 894540410e2768be1cb679b5108fc8c694ca02d3
ms.lasthandoff: 03/17/2017

---
# <a name="call-class"></a>call 클래스
`call` 메시징 블록은 메시지를 받을 때 지정된 함수를 호출하는 순서가 지정된 다중 소스 `target_block`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 이 블록에 전파 하는 메시지의 페이로드 유형입니다.  
  
 `_FunctorType`  
 이 블록을 수락할 수 있는 함수의 서명입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[호출](#ctor)|오버로드됨. 생성 된 `call` 메시징 블록입니다.|  
|[~ call 소멸자](#dtor)|소멸은 `call` 메시징 블록입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[process_input_messages](#process_input_messages)|입력된 메시지에서 호출 함수를 실행합니다.|  
|[process_message](#process_message)|이 수락 했던 메시지를 처리 `call` 메시징 블록입니다.|  
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.|  
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 에 의해 호출 됩니다는 `send` 메서드를 소스 블록에서 호출 하면 됩니다.|  
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. (재정의 [itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ITarget](itarget-class.md)  
  
 [target_block](target-block-class.md)  
  
 `call`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a>호출 

 생성 된 `call` 메시징 블록입니다.  
  
```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Func`  
 수락 된 각 메시지에 대 한 호출 될 함수입니다.  
  
 `_Filter`  
 제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수  
  
 `_PScheduler`  
 `Scheduler` 의 전파에 대 한 작업이 있는 개체는 `call` 메시징 블록 예약 됩니다.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` 의 전파에 대 한 작업이 있는 개체는 `call` 메시징 블록 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>설명  
 런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.  
  
 형식 `_Call_method` 시그니처가 있는 함수는 `void (T const &)` 이 호출 되는 `call` 메시징 블록 메시지를 처리 합니다.  
  
 형식 `filter_method` 시그니처가 있는 함수는 `bool (T const &)` 이 호출 되는 `call` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.  
  
##  <a name="dtor"></a>~ 호출 

 소멸은 `call` 메시징 블록입니다.  
  
```
~call();
```  
  
##  <a name="process_input_messages"></a>process_input_messages 

 입력된 메시지에서 호출 함수를 실행합니다.  
  
```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
  
##  <a name="process_message"></a>process_message 

 이 수락 했던 메시지를 처리 `call` 메시징 블록입니다.  
  
```
virtual void process_message(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 처리할 메시지에 대 한 포인터입니다.  
  
##  <a name="propagate_message"></a>propagate_message 

 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.  
  
```
virtual message_status propagate_message(
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
  
##  <a name="send_message"></a>send_message 

 메시지를 동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 에 의해 호출 됩니다는 `send` 메서드를 소스 블록에서 호출 하면 됩니다.  
  
```
virtual message_status send_message(
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
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 `supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>반환 값  
 블록은 제공된 메시지를 연기하지 않기 때문에 `true`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [transformer 클래스](transformer-class.md)

