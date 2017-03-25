---
title: "message 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
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
ms.openlocfilehash: c6cc72c1fe9385eabe86194031913b7363d602ff
ms.lasthandoff: 03/17/2017

---
# <a name="message-class"></a>message 클래스
메시징 블록 간에 전달되는 데이터 페이로드를 포함하는 기본 메시지 봉투입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 데이터 형식 메시지 내의 페이로드입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[message](#ctor)|오버로드됨. `message` 개체를 생성합니다.|  
|[~ message 소멸자](#dtor)|소멸은 `message` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[add_ref](#add_ref)|에 대 한 참조 횟수에 추가 된 `message` 개체입니다. 메시지 수명을 확인 하기 위해 참조 가산 필요로 하는 메시지 블록에 사용 합니다.|  
|[msg_id](#msg_id)|ID를 반환 하는 `message` 개체입니다.|  
|[remove_ref](#remove_ref)|에 대 한 참조 횟수를 빼고는 `message` 개체입니다. 메시지 수명을 확인 하기 위해 참조 가산 필요로 하는 메시지 블록에 사용 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[페이로드](#payload)|페이로드는 `message` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `message`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="add_ref"></a>add_ref 

 에 대 한 참조 횟수에 추가 된 `message` 개체입니다. 메시지 수명을 확인 하기 위해 참조 가산 필요로 하는 메시지 블록에 사용 합니다.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>반환 값  
 참조 횟수의 새 값입니다.  
  
##  <a name="ctor"></a>메시지 

 `message` 개체를 생성합니다.  
  
```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```  
  
### <a name="parameters"></a>매개 변수  
 `_P`  
 이 메시지의 페이로드입니다.  
  
 `_Id`  
 이 메시지의 고유 ID입니다.  
  
 `_Msg`  
 참조 또는에 대 한 포인터는 `message` 개체입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터를 사용 하는 생성자는 `message` 인수 throw 개체는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_Msg` 는 `NULL`합니다.  
  
##  <a name="dtor"></a>~ 메시지 

 소멸은 `message` 개체입니다.  
  
```
virtual ~message();
```  
  
##  <a name="msg_id"></a>msg_id 

 ID를 반환 하는 `message` 개체입니다.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>반환 값  
 `runtime_object_identity` 의 `message` 개체입니다.  
  
##  <a name="payload"></a>페이로드 

 페이로드는 `message` 개체입니다.  
  
```
T const payload;
```  
  
##  <a name="remove_ref"></a>remove_ref 

 에 대 한 참조 횟수를 빼고는 `message` 개체입니다. 메시지 수명을 확인 하기 위해 참조 가산 필요로 하는 메시지 블록에 사용 합니다.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>반환 값  
 참조 횟수의 새 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)

