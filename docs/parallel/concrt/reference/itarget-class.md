---
title: "ITarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ITarget
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
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
ms.openlocfilehash: aa9001de9ec35f20cd76f701d6b8acc5de7ffde0
ms.lasthandoff: 02/24/2017

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
 대상 블록에서 허용 하는 메시지 내의 페이로드 데이터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`filter_method`|반환 하는 블록에서 사용 되는 모든 메서드의 시그니처는 `bool` 제공된 된 메시지를 수락 해야 하는지 여부를 결정 하는 값입니다.|  
|`type`|에 대 한 형식 별칭 `T`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[~ ITarget 소멸자](#dtor)|소멸은 `ITarget` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[propagate 메서드](#propagate)|파생된 클래스에서 재정의 되 면 비동기적으로 메시지를 소스 블록에서이 대상 블록 전달 합니다.|  
|[send 메서드](#send)|파생된 클래스에서 재정의 되 면 대상 블록에 동기적으로 메시지를 전달 합니다.|  
|[supports_anonymous_source 메서드](#supports_anonymous_source)|파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의된 메서드가 `true`를 반환할 경우 연기된 메시지를 나중에 사용하려면 소스 링크 레지스트리에서 해당 소스를 식별해야 하기 때문에 대상은 제공된 메시지를 연기할 수 없습니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[link_source 메서드](#link_source)|파생된 클래스에서 재정의 되 면이 지정 된 소스 블록을 연결 `ITarget` 블록입니다.|  
|[unlink_source 메서드](#unlink_source)|파생된 클래스에서 재정의 되 면이 통해 지정 된 소스 블록을 연결 해제 `ITarget` 블록입니다.|  
|[unlink_sources 메서드](#unlink_sources)|파생된 클래스에서 재정의 하는 경우 연결에서이 모든 소스 블록을 해제 `ITarget` 블록입니다.|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ITarget`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namedtora-itarget"></a><a name="dtor"></a>~ ITarget 

 소멸은 `ITarget` 개체입니다.  
  
```
virtual ~ITarget();
```  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 파생된 클래스에서 재정의 되 면이 지정 된 소스 블록을 연결 `ITarget` 블록입니다.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 `ISource` 블록에이 연결 중인 `ITarget` 블록입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에서 직접 호출 하지 않아야는 `ITarget` 블록입니다. 블록을 사용 하 여 함께 연결할는 `link_target` 메서드를 `ISource` 호출 하는 블록의 `link_source` 해당 대상 메서드.  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>전파 

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
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>보내기 

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
 A [message_status](concurrency-namespace-enums.md) 메시지 사용 하기로 하는 대상의 표시 합니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 예외는 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.  
  
 사용 하 여 `send` 메서드 외부 메시지 시작 하 고 네트워크 내에서 메시지를 전파 하 고 교착 상태가 발생할 수 있습니다.  
  
 때 `send` 반환 메시지에 이미 적용 되어 대상 블록으로 전송 또는 대상에 의해 거부 되었습니다.  
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의된 메서드가 `true`를 반환할 경우 연기된 메시지를 나중에 사용하려면 소스 링크 레지스트리에서 해당 소스를 식별해야 하기 때문에 대상은 제공된 메시지를 연기할 수 없습니다.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>반환 값  
 블록에서 연결되지 않은 소스로부터의 메시지를 수락하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 파생된 클래스에서 재정의 되 면이 통해 지정 된 소스 블록을 연결 해제 `ITarget` 블록입니다.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `_PSource`  
 `ISource` 에서 연결이 해제 되 고 차단 `ITarget` 블록입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에서 직접 호출 하지 않아야는 `ITarget` 블록입니다. 사용 하 여 블록을 끊어야는 `unlink_target` 또는 `unlink_targets` 메서드를 `ISource` 호출 하는 블록의 `unlink_source` 해당 대상 메서드.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 파생된 클래스에서 재정의 하는 경우 연결에서이 모든 소스 블록을 해제 `ITarget` 블록입니다.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ISource 클래스](isource-class.md)

