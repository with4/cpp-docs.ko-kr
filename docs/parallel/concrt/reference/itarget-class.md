---
title: ITarget 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9780e4b9ff8950511601b03e8423764c3def77a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="itarget-class"></a>ITarget 클래스
`ITarget` 클래스는 모든 대상 블록에 대한 인터페이스입니다. 대상 블록은 `ISource` 블록에서 제공한 메시지를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 데이터 형식 대상 블록에서 허용 하는 메시지 내의 페이로드입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`filter_method`|반환 하는 블록에서 사용 되는 모든 메서드의 시그니처는 `bool` 제공된 된 메시지를 수락 해야 하는지 여부를 결정 하는 값입니다.|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[~ ITarget 소멸자](#dtor)|소멸 된 `ITarget` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[propagate](#propagate)|파생된 클래스에서 재정의 되 면 비동기적으로 메시지를 소스 블록에서이 대상 블록 전달 합니다.|  
|[send](#send)|파생된 클래스에서 재정의 되 면 대상 블록에 동기적으로 메시지를 전달 합니다.|  
|[supports_anonymous_source](#supports_anonymous_source)|파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의된 메서드가 `true`를 반환할 경우 연기된 메시지를 나중에 사용하려면 소스 링크 레지스트리에서 해당 소스를 식별해야 하기 때문에 대상은 제공된 메시지를 연기할 수 없습니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[link_source](#link_source)|파생된 클래스에서 재정의 되 면이 지정 된 소스 블록에 연결 `ITarget` 블록입니다.|  
|[unlink_source](#unlink_source)|파생된 클래스에서 재정의 되 면이 통해 지정 된 소스 블록을 연결 해제 `ITarget` 블록입니다.|  
|[unlink_sources](#unlink_sources)|파생된 클래스에서 재정의 하는 경우 연결에서이 모든 소스 블록을 해제 `ITarget` 블록입니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ITarget`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a> ~ ITarget 

 소멸 된 `ITarget` 개체입니다.  
  
```
virtual ~ITarget();
```  
  
##  <a name="link_source"></a> link_source 

 파생된 클래스에서 재정의 되 면이 지정 된 소스 블록에 연결 `ITarget` 블록입니다.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 `ISource` 블록에이 연결 중인 `ITarget` 블록입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 직접 호출할 수 없습니다는 `ITarget` 블록입니다. 블록을 사용 하 여 함께 연결할는 `link_target` 메서드를 `ISource` 호출 하는 블록의 `link_source` 해당 대상 메서드.  
  
##  <a name="propagate"></a> 전파 

 파생된 클래스에서 재정의 되 면 비동기적으로 메시지를 소스 블록에서이 대상 블록 전달 합니다.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지로 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 된 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
##  <a name="send"></a> 보내기 

 파생된 클래스에서 재정의 되 면 대상 블록에 동기적으로 메시지를 전달 합니다.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PMessage`  
 `message` 개체에 대한 포인터입니다.  
  
 `_PSource`  
 메시지를 제공 하는 소스 블록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A [message_status](concurrency-namespace-enums.md) 메시지로 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 된 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
 사용 하 여 `send` 메시지 시작 외부 및 네트워크 내에서 메시지를 전파 하는 것은 위험 메서드와 교착 상태가 발생할 수 있습니다.  
  
 때 `send` 반환 메시지에 이미 허용 되었으며 대상 블록으로 전송 또는 대상에 의해 거부 되었습니다.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의된 메서드가 `true`를 반환할 경우 연기된 메시지를 나중에 사용하려면 소스 링크 레지스트리에서 해당 소스를 식별해야 하기 때문에 대상은 제공된 메시지를 연기할 수 없습니다.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>반환 값  
 블록에서 연결되지 않은 소스로부터의 메시지를 수락하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="unlink_source"></a> unlink_source 

 파생된 클래스에서 재정의 되 면이 통해 지정 된 소스 블록을 연결 해제 `ITarget` 블록입니다.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 `ISource` 에서 연결이 해제 되 고 차단 `ITarget` 블록입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 직접 호출할 수 없습니다는 `ITarget` 블록입니다. 사용 하 여 블록을 끊어야는 `unlink_target` 또는 `unlink_targets` 에 대 한 메서드 `ISource` 호출 하는 블록의 `unlink_source` 해당 대상 메서드.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 파생된 클래스에서 재정의 하는 경우 연결에서이 모든 소스 블록을 해제 `ITarget` 블록입니다.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ISource 클래스](isource-class.md)
