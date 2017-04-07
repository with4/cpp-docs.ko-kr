---
title: "message_processor 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
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
ms.openlocfilehash: dff934584179cc58d884be65fdb96cb6c646a4ac
ms.lasthandoff: 03/17/2017

---
# <a name="messageprocessor-class"></a>message_processor 클래스
`message_processor` 클래스는 `message` 개체 처리를 위한 추상 기본 클래스입니다. 메시지 순서에 대한 보장은 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 이 메시지 내의 페이로드의 데이터 형식을 처리 `message_processor` 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[async_send](#async_send)|파생된 클래스에서 재정의 되 면 메시지를 비동기적으로 블록에 배치 합니다.|  
|[sync_send](#sync_send)|파생된 클래스에서 재정의 되 면 메시지를 동기적으로 블록에 배치 합니다.|  
|[대기](#wait)|파생된 클래스에서 재정의 되 면 모든 비동기 작업이 완료 될 때까지 기다립니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|파생된 클래스에서 재정의 되 면 블록으로 전달 메시지 처리를 수행 합니다. 새 메시지가 추가 되 고 큐가 비워 둘 수 발견 될 때마다 한 번씩 호출 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `message_processor`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="async_send"></a>async_send 

 파생된 클래스에서 재정의 되 면 메시지를 비동기적으로 블록에 배치 합니다.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 A `message` 비동기적으로 보낼 개체입니다.  
  
### <a name="remarks"></a>주의  
 프로세서 구현에서는이 메서드를 재정의 해야 합니다.  
  
##  <a name="process_incoming_message"></a>process_incoming_message 

 파생된 클래스에서 재정의 되 면 블록으로 전달 메시지 처리를 수행 합니다. 새 메시지가 추가 되 고 큐가 비워 둘 수 발견 될 때마다 한 번씩 호출 합니다.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>주의  
 메시지 블록 구현은이 메서드를 재정의 해야 합니다.  
  
##  <a name="sync_send"></a>sync_send 

 파생된 클래스에서 재정의 되 면 메시지를 동기적으로 블록에 배치 합니다.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Msg`  
 A `message` 동기적으로 보낼 개체입니다.  
  
### <a name="remarks"></a>주의  
 프로세서 구현에서는이 메서드를 재정의 해야 합니다.  
  
##  <a name="wait"></a>대기 

 파생된 클래스에서 재정의 되 면 모든 비동기 작업이 완료 될 때까지 기다립니다.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>주의  
 프로세서 구현에서는이 메서드를 재정의 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ordered_message_processor 클래스](ordered-message-processor-class.md)

