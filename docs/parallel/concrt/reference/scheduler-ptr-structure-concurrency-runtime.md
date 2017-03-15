---
title: "scheduler_ptr 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplinterface/concurrency::scheduler_ptr
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 022b5fafc437a8103fe17967a9a5ea54d5b82a39
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerptr-structure"></a>scheduler_ptr 구조체
스케줄러에 대한 포인터를 나타냅니다. 이 클래스는 shared_ptr을 사용하는 공유 수명 또는 원시 포인터를 사용하는 일반 참조의 사양을 허용하기 위해 존재합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[scheduler_ptr:: scheduler_ptr 생성자](#ctor)|오버로드됨. shared_ptr에서 스케줄러에 대한 스케줄러 포인터를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[scheduler_ptr:: get 메서드](#get)|스케줄러에 대한 원시 포인터를 반환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[scheduler_ptr:: operator bool 연산자](#operator_bool)|스케줄러 포인터가 null이 아닌지 여부를 테스트합니다.|  
|[scheduler_ptr:: operator-&gt; 연산자](#operator_ptr)|포인터처럼 작동합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `scheduler_ptr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** pplinterface.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namegeta--schedulerptrget-method"></a><a name="get"></a>scheduler_ptr:: get 메서드  
 스케줄러에 대한 원시 포인터를 반환합니다.  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-nameoperatorboola--schedulerptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr:: operator bool   
 스케줄러 포인터가 null이 아닌지 여부를 테스트합니다.  
  
' ' 연산자 bool() const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
scheduler_interface * operator->() const;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
명시적 scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);</scheduler_interface>

명시적 scheduler_ptr (_In_opt_ scheduler_interface pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)

