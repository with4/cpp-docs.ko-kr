---
title: task_completion_event 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b22b77affd41aa60769543ae2bea2ed495084ae
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="taskcompletionevent-class"></a>task_completion_event 클래스
`task_completion_event` 클래스를 사용하면 조건이 충족될 때까지 작업 실행을 지연하거나 외부 이벤트에 대한 응답으로 작업을 시작할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_ResultType`  
 이 `task_completion_event` 클래스의 결과 형식입니다.  
  
 `T`  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[task_completion_event](#ctor)|`task_completion_event` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[set](#set)|오버로드됨. 작업 완료 이벤트를 설정합니다.|  
|[set_exception](#set_exception)|오버로드됨. 이 이벤트와 연결된 모든 작업에 대한 예외를 전파합니다.|  
  
## <a name="remarks"></a>설명  
 완료되는 작업을 만들어야 하는 시나리오를 사용 중이어서 이후 시점에 연속 실행을 예약해야 하는 경우 작업 완료 이벤트에서 작성한 작업을 사용합니다. `task_completion_event`의 형식은 작성하는 작업과 같아야 합니다. 해당 형식의 값을 사용하여 작업 완료 이벤트에 대해 set 메서드를 호출하면 연결된 작업이 완료되며 해당 값이 연속에 대한 결과로 제공됩니다.  
  
 작업 완료 이벤트가 발생하지 않으면 해당 이벤트에서 작성된 모든 작업은 이벤트 소멸 시 취소됩니다.  
  
 `task_completion_event`는 스마트 포인터처럼 동작하며 값으로 전달해야 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `task_completion_event`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="set"></a> 설정 

 작업 완료 이벤트를 설정합니다.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Result`  
 이 이벤트를 설정 하려면 결과입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 반환 `true` 이벤트를 설정 하는 데 성공한 것입니다. 반환 `false` 이벤트 이미 설정 된 경우.  
  
### <a name="remarks"></a>설명  
 여러 개 있는 경우 또는 동시 호출을 `set`은 첫 번째 호출에 성공 하 고 (있는 경우)는 결과 작업 완료 이벤트에 저장 됩니다. 나머지 집합 무시 되며 메서드가 false를 반환 합니다. 작업 완료 이벤트를 설정 하면 모든 작업에서 만든 이벤트 즉시 완료 하 고 해당 연속 있는 경우 예약 됩니다. 작업 완료 개체는 `_ResultType` 이외의 `void` 작업의 연속을 값에 전달 합니다.  
  
##  <a name="set_exception"></a> set_exception 

 이 이벤트와 연결된 모든 작업에 대한 예외를 전파합니다.  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>매개 변수  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="ctor"></a> task_completion_event 

 `task_completion_event` 개체를 생성합니다.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
