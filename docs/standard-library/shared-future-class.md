---
title: "shared_future 클래스 | Microsoft Docs"
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
  - "future/std::shared_future"
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shared_future 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an *asynchronous return object*.  In contrast with a [future](../standard-library/future-class.md) object, an *asynchronous provider* can be associated with any number of `shared_future` objects.  
  
## 구문  
  
```  
template<class Ty>  
class shared_future;  
```  
  
## 설명  
 Do not call any methods other than `valid`, `operator=`, and the destructor on a `shared_future` object that's *empty*.  
  
 `shared_future` objects are not synchronized.  Calling methods on the same object from multiple threads introduces a data race that has unpredictable results.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[shared\_future::shared\_future 생성자](../Topic/shared_future::shared_future%20Constructor.md)|`shared_future` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[shared\_future::get 메서드](../Topic/shared_future::get%20Method.md)|Retrieves the result that's stored in the *associated asynchronous state*.|  
|[shared\_future::valid 메서드](../Topic/shared_future::valid%20Method.md)|Specifies whether the object is not empty.|  
|[shared\_future::wait 메서드](../Topic/shared_future::wait%20Method.md)|Blocks the current thread until the associated asynchronous state is ready.|  
|[shared\_future::wait\_for 메서드](../Topic/shared_future::wait_for%20Method.md)|Blocks until the associated asynchronous state is ready or until the specified time has elapsed.|  
|[shared\_future::wait\_until 메서드](../Topic/shared_future::wait_until%20Method.md)|Blocks until the associated asynchronous state is ready or until a specified point in time.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[shared\_future::operator\= 연산자](../Topic/shared_future::operator=%20Operator.md)|Assigns a new associated asynchronous state.|  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)