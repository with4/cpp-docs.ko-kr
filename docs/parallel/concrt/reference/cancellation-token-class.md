---
title: "cancellation_token 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
dev_langs: C++
helpviewer_keywords: cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a27bb4221e1a8db19f0dd7be37bb6ca3966635de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cancellationtoken-class"></a>cancellation_token 클래스
`cancellation_token` 클래스는 일부 작업을 취소하도록 요청되었는지 여부를 확인하는 기능을 나타냅니다. 지정된 토큰을 `task_group`, `structured_task_group` 또는 `task`와 연결하여 암시적 취소를 제공할 수 있습니다. 연결된 `cancellation_token_source`가 취소된 경우 취소를 폴링하거나 콜백을 등록할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[cancellation_token](#ctor)||  
|[~ cancellation_token 소멸자](#dtor)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[deregister_callback](#deregister_callback)|등록 시 반환된 `register` 개체를 기반으로 `cancellation_token_registration` 메서드를 통해 이전에 등록한 콜백을 제거합니다.|  
|[is_cancelable](#is_cancelable)|이 토큰을 취소할 수 있는지 여부를 나타내는 값을 반환합니다.|  
|[is_canceled](#is_canceled)|토큰이 취소된 경우 `true`를 반환합니다.|  
|[none](#none)|취소에 영향을 받을 수 없는 취소 토큰을 반환합니다.|  
|[register_callback](#register_callback)|토큰에 콜백 함수를 등록합니다. 만약 토큰이 취소되면 콜백이 만들어집니다. 이 메서드가 호출된 시점에 토큰이 이미 취소된 경우, 동기적으로 즉시 콜백이 만들어집니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `cancellation_token`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** pplcancellation_token.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a>~ cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="ctor"></a>cancellation_token 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
##  <a name="deregister_callback"></a>deregister_callback 

 등록 시 반환된 `register` 개체를 기반으로 `cancellation_token_registration` 메서드를 통해 이전에 등록한 콜백을 제거합니다.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Registration`  
 `cancellation_token_registration` 개체는 등록을 취소할 콜백에 해당합니다. `register` 메서드에 대한 호출에서 이 토큰이 이전에 반환됐어야 합니다.  
  
##  <a name="is_cancelable"></a>is_cancelable 

 이 토큰을 취소할 수 있는지 여부를 나타내는 값을 반환합니다.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 토큰을 취소할 수 있는지 여부를 나타냅니다.  
  
##  <a name="is_canceled"></a>is_canceled 

 토큰이 취소된 경우 `true`를 반환합니다.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>반환 값  
 토큰이 취소되면 값은 `true`이고, 그렇지 않으면 값은 `false`입니다.  
  
##  <a name="none"></a>없음 

 취소에 영향을 받을 수 없는 취소 토큰을 반환합니다.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>반환 값  
 취소할 수 없는 취소 토큰입니다.  
  
##  <a name="operator_neq"></a>operator! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq"></a>연산자 = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq_eq"></a>연산자 = = 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="register_callback"></a>register_callback 

 토큰에 콜백 함수를 등록합니다. 만약 토큰이 취소되면 콜백이 만들어집니다. 이 메서드가 호출된 시점에 토큰이 이미 취소된 경우, 동기적으로 즉시 콜백이 만들어집니다.  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 이 `cancellation_token`이 취소될 때 콜백되는 함수 개체의 형식입니다.  
  
 `_Func`  
 이 `cancellation_token`이 취소되었을 때 콜백되는 함수 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 등록된 콜백의 등록을 해제하고 콜백이 이루어지지 않도록 하기 위해 `cancellation_token_registration` 메서드에서 이용할 수 있는 `deregister` 개체입니다. 합니다는 [invalid_operation](invalid-operation-class.md) 예외에서 호출 되는 `cancellation_token` 사용 하 여 만든 개체는 [cancellation_token:: none](#none) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
