---
title: "structured_task_group 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f8d2b9cdc71b6e8a7a0fe9e3bf3d3d3306af1da
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="structuredtaskgroup-class"></a>structured_task_group 클래스
`structured_task_group` 클래스는 구조화된 병렬 작업 컬렉션을 나타냅니다. `task_handle` 개체를 사용하여 개별 병렬 작업을 `structured_task_group`에 대기시킨 다음 완료되기를 기다리거나 실행이 완료되기 전에 작업 그룹을 취소합니다. 이 경우 실행이 시작되지 않은 작업이 모두 중단됩니다.  
  
## <a name="syntax"></a>구문  
  
```
class structured_task_group;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[structured_task_group](#ctor)|오버로드됨. 새 `structured_task_group` 개체를 생성합니다.|  
|[~ structured_task_group 소멸자](#dtor)|`structured_task_group` 개체를 제거합니다. 중 하나를 호출 해야는 `wait` 또는 `run_and_wait` 소멸자 실행 전에 개체의 메서드를 소멸자는 실행 되지 않는 경우의 결과로 인 한 스택 해제는 예외입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[cancel](#cancel)|이 작업 그룹에서 시작한 작업의 하위 트리를 취소 하려는 시도를 만듭니다. 작업 그룹에 예약 된 모든 작업은 전이적으로 취소 가능한 경우.|  
|[is_canceling](#is_canceling)|작업 그룹 현재 취소 중은 여부 호출자에 게 알립니다. 이 반드시을 나타내지 않는 `cancel` 메서드가 `structured_task_group` 개체 (반드시 반환 하려면이 메서드 `true`). 대/소문자는 것입니다는 `structured_task_group` 인라인으로 실행 개체 및 작업 그룹을 추가로 구성 작업 트리에서 취소 되었습니다. 이 경우 런타임에서 취소가를 통해 이동 하는 미리 확인할 수 `structured_task_group` 개체 `true` 도 반환 됩니다.|  
|[run](#run)|오버로드됨. 작업을 예약는 `structured_task_group` 개체입니다. 호출자의 수명을 관리 하는 `task_handle` 에 전달 된 개체는 `_Task_handle` 매개 변수입니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.|  
|[run_and_wait](#run_and_wait)|오버로드됨. 사용 하 여 인라인 호출 컨텍스트에서 실행 하는 작업을 예약 된 `structured_task_group` 전체 취소 지원에 대 한 개체입니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run_and_wait`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다. 함수는 다음에 사용 될 때까지 대기는 `structured_task_group` 개체 완료 되거나 취소 되었습니다.|  
|[wait](#wait)|에 사용 될 때까지 대기는 `structured_task_group` 완료 또는 취소 됩니다.|  
  
## <a name="remarks"></a>설명  
 심각한 제한의 사용에는 여러 가지가 `structured_task_group` 성능 개선을 위해 개체:  
  
-   단일 `structured_task_group` 다중 스레드에서 개체를 사용할 수 없습니다. 모든 작업에는 `structured_task_group` 개체를 만든 스레드 개체를 수행 해야 합니다. 이 규칙에 두 가지 예외는 멤버 함수 `cancel` 및 `is_canceling`합니다. 개체는 람다 식의 캡처 목록에 없을 수 있습니다 및 작업이 취소 작업 중 하나를 사용 하는 않은 경우에 태스크 내에서 사용할 수 있습니다.  
  
-   에 예약 된 모든 작업이 `structured_task_group` 개체를 사용 하 여 예약 된 `task_handle` 의 수명을 명시적으로 관리 해야 하는 개체입니다.  
  
-   여러 그룹은 반드시 중첩 된 순서에만 사용할 수 있습니다. 두 개 `structured_task_group` 선언 된 개체, (내부 하나)를 선언 되 고 두 번째 항목을 제외한 모든 방법 전에 소멸 되어야 `cancel` 또는 `is_canceling` 라고 하는 첫 번째 (외부 하나). 여러를 선언 하는 것의 경우이 조건이 true `structured_task_group` 를 큐에 추가 된 작업의 경우와 같거나 기능적으로 중첩 된 범위 내의 개체는 `structured_task_group` 통해는 `run` 또는 `run_and_wait` 메서드.  
  
-   일반 달리 `task_group` 클래스의 모든 상태는 `structured_task_group` 클래스는 최종 합니다. 그룹에 작업을 큐 대기하고 완료되기를 기다린 후에 다시 같은 그룹을 사용할 수 없습니다.  
  
 자세한 내용은 참조 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `structured_task_group`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="cancel"></a> 취소 

 이 작업 그룹에서 시작한 작업의 하위 트리를 취소 하려는 시도를 만듭니다. 작업 그룹에 예약 된 모든 작업은 전이적으로 취소 가능한 경우.  
  
```
void cancel();
```  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [취소](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)합니다.  
  
##  <a name="is_canceling"></a> is_canceling 

 작업 그룹 현재 취소 중은 여부 호출자에 게 알립니다. 이 반드시을 나타내지 않는 `cancel` 메서드가 `structured_task_group` 개체 (반드시 반환 하려면이 메서드 `true`). 대/소문자는 것입니다는 `structured_task_group` 인라인으로 실행 개체 및 작업 그룹을 추가로 구성 작업 트리에서 취소 되었습니다. 이 경우 런타임에서 취소가를 통해 이동 하는 미리 확인할 수 `structured_task_group` 개체 `true` 도 반환 됩니다.  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>반환 값  
 여부를 `structured_task_group` 취소 중가 (또는 곧 되도록 보장) 개체입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [취소](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)합니다.  
  
##  <a name="run"></a> 실행 

 작업을 예약는 `structured_task_group` 개체입니다. 호출자의 수명을 관리 하는 `task_handle` 에 전달 된 개체는 `_Task_handle` 매개 변수입니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.  
  
```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 작업 핸들의 본문을 실행 하기 위해 호출 될 함수 개체의 형식입니다.  
  
 `_Task_handle`  
 예약 된 작업에 대 한 핸들입니다. 호출자에이 개체의 수명에 대 한 책임을 참고 합니다. 런타임에서 계속 될 때까지 라이브로 `wait` 또는 `run_and_wait` 이 메서드가 호출 된 `structured_task_group` 개체입니다.  
  
 `_Placement`  
 `_Task_handle` 매개 변수가 나타내는 작업을 실행해야 할 위치에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 런타임에서이 메서드에 전달 하는 작업 함수의 복사본을 만듭니다. 이 메서드에 전달 하는 함수 개체에서 발생 하는 모든 상태 변경을 해당 함수 개체의 복사본에 나타나지 않습니다.  
  
 경우는 `structured_task_group` 스택 해제 예외에서의 결과로 소멸을 불필요 하는 호출 중 하나로 보장 하기 위해는 `wait` 또는 `run_and_wait` 메서드. 이 경우 소멸자가 적절 하 게 취소 되며 나타내는 작업에 대 한 대기는 `_Task_handle` 매개 변수를 완료 합니다.  
  
 Throw는 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) 태스크가 처리 하는 경우 예외에서 주어진는 `_Task_handle` 매개 변수를 통해 작업 그룹 개체에 이미 예약 되어는 `run` 메서드에 대 한 중간 호출이 되었습니다 중 하나는 `wait` 또는 `run_and_wait` 메서드를 해당 작업 그룹입니다.  
  
##  <a name="run_and_wait"></a> run_and_wait 

 사용 하 여 인라인 호출 컨텍스트에서 실행 하는 작업을 예약 된 `structured_task_group` 전체 취소 지원에 대 한 개체입니다. 경우는 `task_handle` 에 대 한 매개 변수로 전달 `run_and_wait`의 수명을 관리 하는 것에 대 한 호출자가는 `task_handle` 개체입니다. 함수는 다음에 사용 될 때까지 대기는 `structured_task_group` 개체 완료 되거나 취소 되었습니다.  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 작업을 실행하기 위해 호출될 함수 개체의 형식입니다.  
  
 `_Task_handle`  
 인라인 호출 컨텍스트에에서 실행 되는 작업에 대 한 핸들입니다. 호출자에이 개체의 수명에 대 한 책임을 참고 합니다. 런타임에서 계속 될 때까지 라이브로 `run_and_wait` 메서드 실행을 완료 합니다.  
  
 `_Func`  
 함수는 작업의 본문을 호출 하기 위해입니다. 람다 또는 서명 사용 하 여 함수 호출 연산자의 버전을 지 원하는 다른 개체 수도 `void operator()()`합니다.  
  
### <a name="return-value"></a>반환 값  
 작업과 작업 중 하나에서 throw 되는 예외 또는 명시적인 취소 작업으로 인해 대기 충족 하는지 여부를 나타내는 값 또는 작업 그룹이 취소 되었습니다. 자세한 내용은 참조 [task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>설명  
 이 예약 된 작업 중 하나 이상을 참고 `structured_task_group` 개체 인라인 호출 컨텍스트에서 실행할 수 있습니다.  
  
 이 예약 된 작업의 하나 이상이 `structured_task_group` 예외를 throw 하는 개체, 런타임에서 이러한 예외를 하나를 선택 하 고 전파에 대 한 호출에서 `run_and_wait` 메서드.  
  
 이 함수가 반환된 후 `structured_task_group` 개체는 최종 상태로 간주되므로 사용할 수 없습니다. 반환한 후의 `run_and_wait` 메서드가 정의 되지 않은 동작이 발생을 반환 합니다.  
  
 두이 방법 중 하나를 호출 해야 실행 비 예외 경로 또는 `wait` 의 소멸자 보다 먼저 메서드는 `structured_task_group` 실행 합니다.  
  
##  <a name="ctor"></a> structured_task_group 

 새 `structured_task_group` 개체를 생성합니다.  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>매개 변수  
 `_CancellationToken`  
 이 구조적된 작업 그룹에 연결할 취소 토큰입니다. 구조적된 작업 그룹은 토큰이 취소 될 때 취소 됩니다.  
  
### <a name="remarks"></a>설명  
 취소 토큰을 사용하는 생성자는 토큰에 연결된 소스가 취소될 때 취소될 `structured_task_group`을 만듭니다. 명시적 취소 토큰을 제공이 구조적된 작업 그룹에 다른 토큰이 있거나 토큰이 없는 부모 그룹에서의 암시적 취소 참여 하지 않도록 격리 됩니다.  
  
##  <a name="dtor"></a> ~structured_task_group 

 `structured_task_group` 개체를 제거합니다. 중 하나를 호출 해야는 `wait` 또는 `run_and_wait` 소멸자 실행 전에 개체의 메서드를 소멸자는 실행 되지 않는 경우의 결과로 인 한 스택 해제는 예외입니다.  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행 되 고 (예를 들어 스택 해제 되지 않음 예외로 인해) 정상 실행의 결과로 `wait` 나 `run_and_wait` 메서드도 호출 되지 않은, 소멸자 throw 될 수 있습니다는 [missing_wait](missing-wait-class.md) 예외입니다.  
  
##  <a name="wait"></a> 대기 

 에 사용 될 때까지 대기는 `structured_task_group` 완료 또는 취소 됩니다.  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>반환 값  
 작업과 작업 중 하나에서 throw 되는 예외 또는 명시적인 취소 작업으로 인해 대기 충족 하는지 여부를 나타내는 값 또는 작업 그룹이 취소 되었습니다. 자세한 내용은 참조 [task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>설명  
 이 예약 된 작업 중 하나 이상을 참고 `structured_task_group` 개체 인라인 호출 컨텍스트에서 실행할 수 있습니다.  
  
 이 예약 된 작업의 하나 이상이 `structured_task_group` 예외를 throw 하는 개체, 런타임에서 이러한 예외를 하나를 선택 하 고 전파에 대 한 호출에서 `wait` 메서드.  
  
 이 함수가 반환된 후 `structured_task_group` 개체는 최종 상태로 간주되므로 사용할 수 없습니다. 반환한 후의 `wait` 메서드가 정의 되지 않은 동작이 발생을 반환 합니다.  
  
 두이 방법 중 하나를 호출 해야 실행 비 예외 경로 또는 `run_and_wait` 의 소멸자 보다 먼저 메서드는 `structured_task_group` 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [task_group 클래스](task-group-class.md)   
 [task_handle 클래스](task-handle-class.md)
