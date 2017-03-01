---
title: "ordered_message_processor 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ordered_message_processor
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
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
ms.openlocfilehash: a9653c8eb5f05e56fd7812d334575e62dc101d63
ms.lasthandoff: 02/24/2017

---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor 클래스
`ordered_message_processor`는 메시지 블록이 수신된 순서대로 메시지를 처리할 수 있도록 하는 `message_processor`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 프로세서에 의해 처리 되는 메시지의 페이로드 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ordered_message_processor 생성자](#ctor)|`ordered_message_processor` 개체를 생성합니다.|  
|[~ ordered_message_processor 소멸자](#dtor)|소멸은 `ordered_message_processor` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[async_send 메서드](#async_send)|비동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 처리 작업을 시작 합니다. (재정의 [message_processor:: async_send](message-processor-class.md#async_send).)|  
|[initialize 메서드](#initialize)|초기화는 `ordered_message_processor` 적절 한 콜백 함수, 스케줄러 및 일정 그룹 개체입니다.|  
|[initialize_batched_processing 메서드](#initialize_batched_processing)|일관 처리된 메시지 처리 초기화|  
|[sync_send 메서드](#sync_send)|동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 처리 작업을 시작 합니다. (재정의 [message_processor:: sync_send](message-processor-class.md#sync_send).)|  
|[wait 메서드](#wait)|모든 비동기 처리 작업의 블록을 삭제 하기 전에 완료 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 되는 특정 프로세서 관련 스핀 대기 합니다. (재정의 [message_processor:: wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[process_incoming_message 메서드](#process_incoming_message)|비동기적으로 호출 되는 처리 함수입니다. 메시지를 큐에서 제거 하 고 처리를 시작 합니다. (재정의 [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 비동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 처리 작업을 시작 합니다.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 메시지에 대 한 포인터입니다.  
  
##  <a name="a-nameinitializea-initialize"></a><a name="initialize"></a>초기화 

 초기화는 `ordered_message_processor` 적절 한 콜백 함수, 스케줄러 및 일정 그룹 개체입니다.  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PScheduler`  
 간단한 작업을 예약 하는 데 사용할 스케줄러에 대 한 포인터입니다.  
  
 `_PScheduleGroup`  
 간단한 작업을 예약 하는 데 사용할 일정 그룹에 대 한 포인터입니다.  
  
 `_Handler`  
 콜백 중에 호출 처리기 함수입니다.  
  
##  <a name="a-nameinitializebatchedprocessinga-initializebatchedprocessing"></a><a name="initialize_batched_processing"></a>initialize_batched_processing 

 일관 처리된 메시지 처리 초기화  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Processor`  
 콜백 중에 호출 되는 프로세서 구조 함수입니다.  
  
 `_Propagator`  
 콜백 중에 호출 되는 전파자 구조 함수입니다.  
  
##  <a name="a-namectora-orderedmessageprocessor"></a><a name="ctor"></a>ordered_message_processor 

 `ordered_message_processor` 개체를 생성합니다.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>주의  
 이 `ordered_message_processor` 될 때까지 비동기 또는 동기 처리기 일정지 것입니다는 `initialize` 함수를 호출 합니다.  
  
##  <a name="a-namedtora-orderedmessageprocessor"></a><a name="dtor"></a>~ ordered_message_processor 

 소멸은 `ordered_message_processor` 개체입니다.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>주의  
 프로세서를 삭제 하기 전에 모든 대기 중인 비동기 작업에 대 한 대기 합니다.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 비동기적으로 호출 되는 처리 함수입니다. 메시지를 큐에서 제거 하 고 처리를 시작 합니다.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 동기적으로 메시지를 큐에 대기 하 고 이미 수행 되지 않은 경우 처리 작업을 시작 합니다.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 메시지에 대 한 포인터입니다.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>대기 

 모든 비동기 처리 작업의 블록을 삭제 하기 전에 완료 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 되는 특정 프로세서 관련 스핀 대기 합니다.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)

