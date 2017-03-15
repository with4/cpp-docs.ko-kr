---
title: "target_block 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::target_block
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 0137e95d0d5015fd2e8d18d85388c16ab25a2e9c
ms.lasthandoff: 02/24/2017

---
# <a name="targetblock-class"></a>target_block 클래스
`target_block` 클래스는 대상 전용 블록에 대해 기본 링크 관리 기능 및 오류 검사를 제공하는 추상 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_SourceLinkRegistry`  
 소스 링크를 저장에 사용할 링크 레지스트리.  
  
 `_MessageProcessorType`  
 메시지 처리에 대 한 프로세서 종류입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`source_iterator`|에 대 한 반복기의 형식에서 `source_link_manager` 이 `target_block` 개체입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[target_block 생성자](#ctor)|`target_block` 개체를 생성합니다.|  
|[~ target_block 소멸자](#dtor)|소멸은 `target_block` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[propagate 메서드](#propagate)|소스 블록에서이 대상 블록에 메시지를 비동기적으로 전달 합니다.|  
|[send 메서드](#send)|소스 블록에서이 대상 블록에 메시지를 동기적으로 전달 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[async_send 메서드](#async_send)|처리를 위해 메시지를 비동기적으로 보냅니다.|  
|[decline_incoming_messages 메서드](#decline_incoming_messages)|새 메시지를 거부 해야 하는 블록을 나타냅니다.|  
|[enable_batched_processing 메서드](#enable_batched_processing)|이 블록에 대한 일괄 처리를 할 수 있도록 합니다.|  
|[initialize_target 메서드](#initialize_target)|기본 개체를 초기화합니다. 구체적으로 `message_processor` 개체를 초기화 해야 합니다.|  
|[link_source 메서드](#link_source)|이 지정 된 소스 블록을 연결 `target_block` 개체입니다.|  
|[process_input_messages 메서드](#process_input_messages)|입력으로 받은 메시지를 처리합니다.|  
|[process_message 메서드](#process_message)|파생 클래스에 재정의된 경우 이 `target_block` 개체가 수락했던 메시지를 처리합니다.|  
|[propagate_message 메서드](#propagate_message)|파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `target_block` 개체입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.|  
|[register_filter 메서드](#register_filter)|받은 모든 메시지에 대해 호출 되는 필터 메서드를 등록 합니다.|  
|[remove_sources 메서드](#remove_sources)|처리 중인 비동기 보내기 작업이 완료 될 때까지 기다린 후 모든 원본 연결을 끊습니다.|  
|[send_message 메서드](#send_message)|파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 동기적으로 전달 된 `ISource` 이 블록 `target_block` 개체입니다. 에 의해 호출 됩니다는 `send` 메서드를 소스 블록에서 호출 하면 됩니다.|  
|[sync_send 메서드](#sync_send)|동기적으로 처리를 위해 메시지를 보냅니다.|  
|[unlink_source 메서드](#unlink_source)|이 통해 지정 된 소스 블록을 연결 해제 `target_block` 개체입니다.|  
|[unlink_sources 메서드](#unlink_sources)|이 모든 소스 블록의 연결을 해제 `target_block` 개체입니다. (재정의 [itarget:: Unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends 메서드](#wait_for_async_sends)|모든 비동기 전파가 완료 될 때까지 기다립니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 처리를 위해 메시지를 비동기적으로 보냅니다.  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 보내는 메시지에 대 한 포인터입니다.  
  
##  <a name="a-namedeclineincomingmessagesa-declineincomingmessages"></a><a name="decline_incoming_messages"></a>decline_incoming_messages 

 새 메시지를 거부 해야 하는 블록을 나타냅니다.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 소멸 진행 중인 동안 새로운 메시지가 거부 되도록 소멸자에 의해 호출 됩니다.  
  
##  <a name="a-nameenablebatchedprocessinga-enablebatchedprocessing"></a><a name="enable_batched_processing"></a>enable_batched_processing 

 이 블록에 대한 일괄 처리를 할 수 있도록 합니다.  
  
```
void enable_batched_processing();
```  
  
##  <a name="a-nameinitializetargeta-initializetarget"></a><a name="initialize_target"></a>initialize_target 

 기본 개체를 초기화합니다. 구체적으로 `message_processor` 개체를 초기화 해야 합니다.  
  
```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PScheduler`  
 작업을 예약 하는 데 사용할 스케줄러입니다.  
  
 `_PScheduleGroup`  
 작업을 예약 하는 데 사용할 일정 그룹입니다.  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 이 지정 된 소스 블록을 연결 `target_block` 개체입니다.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 에 대 한 포인터는 `ISource` 블록 연결 되어야 하는 것입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에서 직접 호출 하지 않아야는 `target_block` 개체입니다. 블록을 사용 하 여 함께 연결할는 `link_target` 메서드를 `ISource` 호출 하는 블록의 `link_source` 해당 대상 메서드.  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 입력으로 받은 메시지를 처리합니다.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
  
##  <a name="a-nameprocessmessagea-processmessage"></a><a name="process_message"></a>process_message 

 파생 클래스에 재정의된 경우 이 `target_block` 개체가 수락했던 메시지를 처리합니다.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>전파 

 소스 블록에서이 대상 블록에 메시지를 비동기적으로 전달 합니다.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `target_block` 개체입니다. 에 의해 호출 됩니다는 `propagate` 메서드를 소스 블록에서 호출 하면 됩니다.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
##  <a name="a-nameregisterfiltera-registerfilter"></a><a name="register_filter"></a>register_filter 

 받은 모든 메시지에 대해 호출 되는 필터 메서드를 등록 합니다.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Filter`  
 필터 메서드입니다.  
  
##  <a name="a-nameremovesourcesa-removesources"></a><a name="remove_sources"></a>remove_sources 

 처리 중인 비동기 보내기 작업이 완료 될 때까지 기다린 후 모든 원본 연결을 끊습니다.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>주의  
 모든 대상 블록의 소멸자에서 원본을 제거 하려면이 루틴을 호출 해야 합니다.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>보내기 

 소스 블록에서이 대상 블록에 메시지를 동기적으로 전달 합니다.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
 사용 하 여 `send` 메서드 외부 메시지 시작 하 고 네트워크 내에서 메시지를 전파 하 고 교착 상태가 발생할 수 있습니다.  
  
 때 `send` 반환 메시지에 이미 적용 되어 대상 블록으로 전송 또는 대상에 의해 거부 되었습니다.  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 동기적으로 전달 된 `ISource` 이 블록 `target_block` 개체입니다. 에 의해 호출 됩니다는 `send` 메서드를 소스 블록에서 호출 하면 됩니다.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 블록 반환 `declined` 파생된 클래스에서 재정의 되지 않는 경우.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 동기적으로 처리를 위해 메시지를 보냅니다.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 보내는 메시지에 대 한 포인터입니다.  
  
##  <a name="a-namectora-targetblock"></a><a name="ctor"></a>target_block 

 `target_block` 개체를 생성합니다.  
  
```
target_block();
```  
  
##  <a name="a-namedtora-targetblock"></a><a name="dtor"></a>~ target_block 

 소멸은 `target_block` 개체입니다.  
  
```
virtual ~target_block();
```  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 이 통해 지정 된 소스 블록을 연결 해제 `target_block` 개체입니다.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 에 대 한 포인터는 `ISource` 블록 연결을 끊을 하는 것입니다.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 이 모든 소스 블록의 연결을 해제 `target_block` 개체입니다.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="a-namewaitforasyncsendsa-waitforasyncsends"></a><a name="wait_for_async_sends"></a>wait_for_async_sends 

 모든 비동기 전파가 완료 될 때까지 기다립니다.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 모든 비동기 작업 시간 블록을 삭제 하기 전에 완료 했을 수 있도록 메시지 블록 소멸자가 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ITarget 클래스](itarget-class.md)

