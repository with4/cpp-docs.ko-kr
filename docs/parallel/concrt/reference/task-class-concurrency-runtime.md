---
title: "작업 클래스(동시성 런타임) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task 클래스"
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 작업 클래스(동시성 런타임)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

PPL\(Parallel Patterns Library\) `task` 클래스입니다.  `task` 개체는 다른 작업과 비동기적이고 동시에 실행할 수 있는 작업과 동시성 런타임에서 병렬 알고리즘에 의해 생성된 병렬 작업을 나타냅니다.  성공적으로 완료된 경우 `_ResultType` 형식 결과를 생성합니다.  `task<void>` 형식의 작업은 결과를 생성하지 않습니다.  작업은 다른 작업과 독립적으로 대기 및 취소할 수 있습니다.  또한 continuations\(`then`\) 및 join\(`when_all`\)과 choice\(`when_any`\) 패턴을 사용하는 다른 작업으로 구성될 수도 있습니다.  
  
## 구문  
  
```  
template <  
   typename _Type  
>  
class task;  
  
template <>  
class task<void>;  
  
template<  
   typename _ReturnType  
>  
class task;  
```  
  
#### 매개 변수  
 `_Type`  
 `T`  
 `_ReturnType`  
 이 작업의 결과 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`result_type`|이 클래스의 개체가 생성하는 결과의 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[task::task 생성자](../Topic/task::task%20Constructor.md)|오버로드됨.  `task` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[task::get 메서드](../Topic/task::get%20Method.md)|오버로드됨.  이 작업으로 생성된 결과를 반환합니다.  작업이 종료 상태가 아닐 경우 `get`에 대한 호출은 작업이 끝날 때까지 대기합니다.  이 메서드는 `void`의 `result_type`을 사용하는 작업에서 호출될 때는 값을 반환하지 않습니다.|  
|[task::is\_apartment\_aware 메서드](../Topic/task::is_apartment_aware%20Method.md)|작업이 Windows 런타임 `IAsyncInfo` 인터페이스의 래핑을 해제하는지 여부 또는 그러한 작업의 하위 작업인지 여부를 확인합니다.|  
|[task::is\_done 메서드\(동시성 런타임\)](../Topic/task::is_done%20Method%20\(Concurrency%20Runtime\).md)|작업이 완료되었는지 여부를 확인합니다.|  
|[task::scheduler 메서드\(동시성 런타임\)](../Topic/task::scheduler%20Method%20\(Concurrency%20Runtime\).md)|이 작업의 스케줄러를 반환합니다.|  
|[task::then 메서드](../Topic/task::then%20Method.md)|오버로드됨.  이 작업에 연속 작업을 추가합니다.|  
|[task::wait 메서드](../Topic/task::wait%20Method.md)|이 작업이 종료 상태에 도달할 때까지 기다립니다.  `wait`은 작업 종속성을 모두 만족하며 백그라운드 작업자에 의해 이미 선택되지 않은 경우 작업을 인라인 실행할 수 있습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[task::operator\!\= 연산자](../Topic/task::operator!=%20Operator.md)|오버로드됨.  두 `task` 개체가 서로 다른 내부 작업을 나타내는지 여부를 확인합니다.|  
|[task::operator\= 연산자](../Topic/task::operator=%20Operator.md)|오버로드됨.  하나의 `task` 개체 콘텐츠를 다른 개체 콘텐츠로 바꿉니다.|  
|[task::operator\=\= 연산자](../Topic/task::operator==%20Operator.md)|오버로드됨.  두 `task` 개체가 동일한 내부 작업을 나타내는지 여부를 확인합니다.|  
  
## 설명  
 자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)을 참조하십시오.  
  
## 상속 계층  
 `task`  
  
## 요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)