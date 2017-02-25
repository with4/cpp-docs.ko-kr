---
title: "task_handle 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::task_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_handle 클래스"
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# task_handle 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_handle` 클래스는 개별 병렬 작업 항목을 나타냅니다.  작업들을 실행하는 데 필요한 지침과 데이터를 캡슐화합니다.  
  
## 구문  
  
```  
template<  
   typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### 매개 변수  
 `_Function`  
 `task_handle` 개체로 표현되는 작업을 실행하기 위해 호출되는 함수 개체의 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[task\_handle::task\_handle 생성자](../Topic/task_handle::task_handle%20Constructor.md)|새 `task_handle` 개체를 생성합니다.  작업은 생성자에 대한 매개 변수로 지정된 함수를 호출하여 수행됩니다.|  
|[task\_handle::~task\_handle 소멸자](../Topic/task_handle::~task_handle%20Destructor.md)|`task_handle` 개체를 소멸시킵니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[task\_handle::operator\(\) 연산자](../Topic/task_handle::operator\(\)%20Operator.md)|함수는 런타임이 작업 핸들의 작업을 수행하기 위해 호출하는 연산자를 호출합니다.|  
  
## 설명  
 `task_handle` 개체는 `structured_task_group` 또는 보다 일반적인 `task_group` 개체와 함께 사용되어 병렬 작업으로 작업을 분리하는 데 사용할 수 있습니다.  자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)을 참조하십시오.  
  
 `task_handle` 개체의 작성자는 동시성 런타임에서 더 이상 필요하지 않을 때까지 만들어진 `task_handle` 개체의 수명을 유지할 책임이 있습니다.  일반적으로 대기열에 추가된 `task_group` 또는 `structured_task_group`의 `wait` 또는 `run_and_wait` 메서드가 호출될 때까지 `task_handle` 개체는 소멸되어서는 안 됩니다.  
  
 `task_handle` 개체는 일반적으로 C\+\+ lambdas와 함께 사용됩니다.  lambda의 실제 형식을 알지 못하기 때문에 [make\_task](../Topic/make_task%20Function.md) 함수는 일반적으로 `task_handle` 개체를 만드는 데 사용됩니다.  
  
 런타임에서 사용자가 `task_handle` 개체로 전달하는 작업 함수의 복사본을 만듭니다.  따라서 `task_handle` 개체로 전달되어 함수 개체에서 발생하는 모든 상태 변경은 해당 함수 개체의 복사본에 나타나지 않습니다.  
  
## 상속 계층  
 `task_handle`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)   
 [structured\_task\_group 클래스](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [make\_task 함수](../Topic/make_task%20Function.md)   
 [task\_group::run 메서드](../Topic/task_group::run%20Method.md)   
 [task\_group::wait 메서드](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait 메서드](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group::run 메서드](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait 메서드](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait 메서드](../Topic/structured_task_group::run_and_wait%20Method.md)