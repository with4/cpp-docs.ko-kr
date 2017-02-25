---
title: "&lt;condition_variable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<condition_variable>"
dev_langs: 
  - "C++"
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;condition_variable&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines the classes [condition\_variable](../standard-library/condition-variable-class.md) and [condition\_variable\_any](../standard-library/condition-variable-any-class.md) that are used to create objects that wait for a condition to become true.  
  
 이 헤더는 다른 ConcRT 메커니즘과 함께 사용할 수 있도록 동시성 런타임 \(ConcRT\)을 사용 합니다.  ConcRT에 대한 자세한 내용은 [동시성 런타임](../parallel/concrt/concurrency-runtime.md)를 참조하십시오.  
  
## 구문  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  여기 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일된 코드에서는 이 헤더가 차단 됩니다.  
  
### 설명  
 Code that waits for a condition variable must also use a `mutex`.  A calling thread must lock the `mutex` before it calls the functions that wait for the condition variable.  The `mutex` is then locked when the called function returns.  The `mutex` is not locked while the thread waits for the condition to become true.  So that there are no unpredictable results, each thread that waits for a condition variable must use the same `mutex` object.  
  
 Objects of type `condition_variable_any` can be used with a mutex of any type.  The type of the mutex that is used does not have to provide the `try_lock` method.  Objects of type `condition_variable` can only be used with a mutex of type `unique_lock<mutex>`.  Objects of this type may be faster than objects of type `condition_variable_any<unique_lock<mutex>>`.  
  
 To wait for an event, first lock the mutex, and then call one of the `wait` methods on the condition variable.  The `wait` call blocks until another thread signals the condition variable.  
  
 *Spurious wakeups* occur when threads that are waiting for condition variables become unblocked without appropriate notifications.  To recognize such spurious wakeups, code that waits for a condition to become true should explicitly check that condition when the code returns from a wait function.  This is usually done by using a loop; you can use `wait(unique_lock<mutex>& lock, Predicate pred)` to perform this loop for you.  
  
```cpp  
while (condition is false)  
    wait for condition variable;  
```  
  
 The `condition_variable_any` and `condition_variable` classes each have three methods that wait for a condition.  
  
-   `wait` waits for an unbounded time period.  
  
-   `wait_until` waits until a specified `time`.  
  
-   `wait_for` waits for a specified `time interval`.  
  
 Each of these methods has two overloaded versions.  One just waits and can wake up spuriously.  The other takes an additional template argument that defines a predicate.  The method does not return until the predicate is `true`.  
  
 Each class also has two methods that are used to notify a condition variable that its condition is `true`.  
  
-   `notify_one` wakes up one of the threads that is waiting for the condition variable.  
  
-   `notify_all` wakes up all of the threads that are waiting for the condition variable.  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [condition\_variable 클래스](../standard-library/condition-variable-class.md)   
 [condition\_variable\_any 클래스](../standard-library/condition-variable-any-class.md)   
 [cv\_status 열거형](../Topic/cv_status%20Enumeration.md)