---
title: "task_handle 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 0fef1ef7b1c02287a0113eb80be413e4a17dc1a4
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="taskhandle-class"></a>task_handle 클래스
`task_handle` 클래스는 개별 병렬 작업 항목을 나타냅니다. 작업을 실행하는 데 필요한 지침 및 데이터를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Function`  
 으로 표시 하는 작업을 실행 하기 위해 호출 될 함수 개체의 종류는 `task_handle` 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[task_handle](#ctor)|새 `task_handle` 개체를 생성합니다. 작업의 작업은 생성자에 매개 변수로 지정 된 함수를 호출 하 여 수행 됩니다.|  
|[~ task_handle 소멸자](#dtor)|소멸은 `task_handle` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator)](#task_handle__operator_call)|작업 핸들의 작업을 수행 하도록 런타임에 호출 하는 함수 호출 연산자.|  
  
## <a name="remarks"></a>설명  
 `task_handle`개체와 함께에서 사용할 수는 `structured_task_group` 또는 더 일반적인 `task_group` 개체를 작업을 병렬 작업으로 분해 합니다. 자세한 내용은 참조 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.  
  
 작성자는 `task_handle` 개체는 만들어진의 수명이 유지 관리를 담당 `task_handle` 동시성 런타임에서 더 이상 필요 될 때까지 개체입니다. 즉, 일반적으로 `task_handle` 될 때까지 개체가 소멸 되지 되어야는 `wait` 또는 `run_and_wait` 의 메서드는 `task_group` 또는 `structured_task_group` 대기 중인를 호출한 합니다.  
  
 `task_handle`개체는 일반적으로 c + + 람다와 함께에서 사용 됩니다. 람다 식의 true 형식을 알지 못하므로 [make_task](concurrency-namespace-functions.md#make_task) 함수를 만드는 데 일반적으로 `task_handle` 개체입니다.  
  
 런타임에서 전달 하는 작업 함수의 복사본을 만듭니다는 `task_handle` 개체입니다. 따라서 모든 변경 사항이 함수에서 발생 하는 개체에 전달 해야 하는 `task_handle` 개체가 해당 함수 개체의 복사본에 표시 되지 것입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `task_handle`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="task_handle__operator_call"></a>operator) 

 작업 핸들의 작업을 수행 하도록 런타임에 호출 하는 함수 호출 연산자.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a>task_handle 

 새 `task_handle` 개체를 생성합니다. 작업의 작업은 생성자에 매개 변수로 지정 된 함수를 호출 하 여 수행 됩니다.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Func`  
 으로 표시 하는 작업을 실행 하기 위해 호출 될 함수는 `task_handle` 개체입니다. 이 람다 함수는 함수에 대 한 포인터 이거나 서명 사용 하 여 함수 호출 연산자의 버전을 지 원하는 모든 개체 `void operator()()`합니다.  
  
### <a name="remarks"></a>주의  
 런타임에서는 생성자에 전달 하는 작업 함수의 복사본을 만듭니다. 따라서 모든 변경 사항이 함수에서 발생 하는 개체에 전달 해야 하는 `task_handle` 개체가 해당 함수 개체의 복사본에 표시 되지 것입니다.  
  
##  <a name="dtor"></a>~ task_handle 

 소멸은 `task_handle` 개체입니다.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [task_group 클래스](task-group-class.md)   
 [structured_task_group 클래스](structured-task-group-class.md)

