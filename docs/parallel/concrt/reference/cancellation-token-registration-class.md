---
title: "cancellation_token_registration 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
dev_langs: C++
helpviewer_keywords: cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70ab8114860a77582a6c9f6276b74122f9505c26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration 클래스
`cancellation_token_registration` 클래스는 `cancellation_token`의 콜백 알림을 나타냅니다. 취소 발생 시 알림을 받는 데 `register`의 `cancellation_token` 메서드를 사용하면 `cancellation_token_registration` 메서드 사용을 통해 더 이상 만들어지지 않는 특정 콜백을 호출자가 요청할 수 있도록 `deregister` 개체가 콜백에 대한 핸들로 반환됩니다.  
  
## <a name="syntax"></a>구문  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[cancellation_token_registration](#ctor)||  
|[~ cancellation_token_registration 소멸자](#dtor)||  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** pplcancellation_token.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a>~ cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="ctor"></a>cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
##  <a name="operator_neq"></a>operator! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq"></a>연산자 = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq_eq"></a>연산자 = = 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
  
### <a name="return-value"></a>반환 값  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
