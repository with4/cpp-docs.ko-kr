---
title: DispatchState 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d3b62248d305e6acebdc8a03b7ef48c2910b28
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691068"
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
|[DispatchState::DispatchState](#ctor)|새 `DispatchState` 개체를 생성합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|버전 관리에 사용 되는이 구조체의 크기입니다.|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|이 컨텍스트에서 시작 했는지 여부를 알려 줍니다.는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. 이 값으로 설정 및 UMS 일정 컨텍스트에만 사용 되며 `0` 다른 모든 실행 컨텍스트와 대 한 합니다.|  
|[DispatchState::m_reserved](#m_reserved)|향후 정보를 전달 하기 위해 예약 되어 비트입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `DispatchState`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a>  Dispatchstate:: Dispatchstate 생성자  
 새 `DispatchState` 개체를 생성합니다.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>  Dispatchstate:: M_dispatchstatesize 데이터 멤버  
 버전 관리에 사용 되는이 구조체의 크기입니다.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  Dispatchstate:: M_fispreviouscontextasynchronouslyblocked 데이터 멤버  
 이 컨텍스트에서 시작 했는지 여부를 알려 줍니다.는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. 이 값으로 설정 및 UMS 일정 컨텍스트에만 사용 되며 `0` 다른 모든 실행 컨텍스트와 대 한 합니다.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>  Dispatchstate:: M_reserved 데이터 멤버  
 향후 정보를 전달 하기 위해 예약 되어 비트입니다.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
