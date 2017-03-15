---
title: "ISource 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ISource
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: db3ba296a96b2e77c0ae7d9be3d0a499fe2e7f76
ms.lasthandoff: 02/24/2017

---
# <a name="isource-class"></a>ISource 클래스
`ISource` 클래스는 모든 소스 블록에 대한 인터페이스입니다. 소스 블록은 `ITarget` 블록에 메시지를 전파합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 소스 블록에 의해 생성 하는 메시지 내의 페이로드 데이터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`source_type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[~ ISource 소멸자](#dtor)|소멸은 `ISource` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accept 메서드](#accept)|파생된 클래스에서 재정의 되 면이 제공 된 메시지를 수락 `ISource` 블록을 호출자에 게 소유권을 전송 합니다.|  
|[acquire_ref 메서드](#acquire_ref)|파생된 클래스에서 재정의 되 면이 대 한 참조 횟수를 획득 `ISource` 삭제를 방지 하기 위해 블록입니다.|  
|[consume 메서드](#consume)|파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 생성 `ISource` 차단 하 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.|  
|[link_target 메서드](#link_target)|파생된 클래스에서 재정의 되 면이 대상 블록을 연결 `ISource` 블록입니다.|  
|[release 메서드](#release)|파생된 클래스에서 재정의 되 면 이전의 성공적인 메시지 예약을 해제 합니다.|  
|[release_ref 메서드](#release_ref)|파생된 클래스에서 재정의 되 면이 대 한 참조 횟수를 해제 `ISource` 블록입니다.|  
|[reserve 메서드](#reserve)|파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 예약 `ISource` 블록입니다.|  
|[unlink_target 메서드](#unlink_target)|파생된 클래스에서 재정의 되 면이 통해 대상 블록을 연결 해제 `ISource` 차단 하는 경우에 이전에 연결이 발견 합니다.|  
|[unlink_targets 메서드](#unlink_targets)|파생된 클래스에서 재정의 하는 경우 연결에서이 모든 대상 블록을 해제 `ISource` 블록입니다.|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>수락 

 파생된 클래스에서 재정의 되 면이 제공 된 메시지를 수락 `ISource` 블록을 호출자에 게 소유권을 전송 합니다.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `accept` 메서드.  
  
### <a name="return-value"></a>반환 값  
 호출자는 이제 소유권을 가진 메시지에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `accept` 메서드는 대상에 의해이 메시지를 제공 하는 동안 `ISource` 블록입니다. 메시지 포인터가 반환에 전달 된 것과에서 다를 수 있습니다는 `propagate` 의 메서드는 `ITarget` 이 원본 메시지의 복사본을 확인 하기로 결정 하는 경우 차단 합니다.  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 파생된 클래스에서 재정의 되 면이 대 한 참조 횟수를 획득 `ISource` 삭제를 방지 하기 위해 블록입니다.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 한 `ITarget` 동안이 소스에 연결 중인 개체의 `link_target` 메서드.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>사용 

 파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 생성 `ISource` 차단 하 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 예약의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `consume` 메서드.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `message` 호출자에 이제 소유권을 가진 개체입니다.  
  
### <a name="remarks"></a>주의  
 `consume` 메서드는 `accept`를 호출 하 여 앞에 항상 있어야 하지만 `reserve` 반환 `true`.  
  
##  <a name="a-namedtora-isource"></a><a name="dtor"></a>~ ISource 

 소멸은 `ISource` 개체입니다.  
  
```
virtual ~ISource();
```  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 파생된 클래스에서 재정의 되 면이 대상 블록을 연결 `ISource` 블록입니다.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 연결 되는 대상 블록에 대 한 포인터 `ISource` 블록입니다.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>릴리스 

 파생된 클래스에서 재정의 되 면 이전의 성공적인 메시지 예약을 해제 합니다.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 예약의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `release` 메서드.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 파생된 클래스에서 재정의 되 면이 대 한 참조 횟수를 해제 `ISource` 블록입니다.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 한 `ITarget` 이 원본의 연결이 해제 되는 개체입니다. 소스 블록은 대상 블록에 대 한 예약 된 리소스를 해제할 수 있습니다.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>예약 

 파생된 클래스에서 재정의 되 면 이전에 제공한이 메시지를 예약 `ISource` 블록입니다.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_MsgId`  
 `runtime_object_identity` 제공 되의 `message` 개체입니다.  
  
 `_PTarget`  
 호출 하는 대상 블록에 대 한 포인터는 `reserve` 메서드.  
  
### <a name="return-value"></a>반환 값  
 `true`메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 호출한 후 `reserve`를 호출 해야 성공 하면 `consume` 또는 `release` 을 얻거나 각각 메시지, 소유권을 포기 하기 위해.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 파생된 클래스에서 재정의 되 면이 통해 대상 블록을 연결 해제 `ISource` 차단 하는 경우에 이전에 연결이 발견 합니다.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 연결이 해제 되는 대상 블록에 대 한 포인터 `ISource` 블록입니다.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 파생된 클래스에서 재정의 하는 경우 연결에서이 모든 대상 블록을 해제 `ISource` 블록입니다.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ITarget 클래스](itarget-class.md)

