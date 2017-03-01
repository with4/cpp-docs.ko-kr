---
title: "DispatchState 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::DispatchState
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 46c2219464e57da4931596e970199549405d02ec
ms.lasthandoff: 02/24/2017

---
# <a name="dispatchstate-structure"></a>DispatchState 구조체
`DispatchState` 구조체는 `IExecutionContext::Dispatch` 메서드에 상태를 전송하는 데 사용됩니다. `IExecutionContext` 인터페이스에 대해 `Dispatch` 메서드가 호출되는 상황을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Dispatchstate:: Dispatchstate 생성자](#ctor)|새 `DispatchState` 개체를 생성합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Dispatchstate:: M_dispatchstatesize 데이터 멤버](#m_dispatchstatesize)|버전 관리에 사용 되는이 구조체의 크기입니다.|  
|[Dispatchstate:: M_fispreviouscontextasynchronouslyblocked 데이터 멤버](#m_fispreviouscontextasynchronouslyblocked)|이 컨텍스트를 입력 했는지를 알려줍니다는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. UMS 일정 컨텍스트에서만에 사용 하 고 값으로 설정 되어이 `0` 다른 모든 실행 컨텍스트에 대 한 합니다.|  
|[Dispatchstate:: M_reserved 데이터 멤버](#m_reserved)|향후 정보를 전달 하기 위해 예약 되어 비트입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `DispatchState`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namectora--dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>Dispatchstate:: Dispatchstate 생성자  
 새 `DispatchState` 개체를 생성합니다.  
  
```
DispatchState();
```  
  
##  <a name="a-namemdispatchstatesizea--dispatchstatemdispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>Dispatchstate:: M_dispatchstatesize 데이터 멤버  
 버전 관리에 사용 되는이 구조체의 크기입니다.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="a-namemfispreviouscontextasynchronouslyblockeda--dispatchstatemfispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>Dispatchstate:: M_fispreviouscontextasynchronouslyblocked 데이터 멤버  
 이 컨텍스트를 입력 했는지를 알려줍니다는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. UMS 일정 컨텍스트에서만에 사용 하 고 값으로 설정 되어이 `0` 다른 모든 실행 컨텍스트에 대 한 합니다.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="a-namemreserveda--dispatchstatemreserved-data-member"></a><a name="m_reserved"></a>Dispatchstate:: M_reserved 데이터 멤버  
 향후 정보를 전달 하기 위해 예약 되어 비트입니다.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)

