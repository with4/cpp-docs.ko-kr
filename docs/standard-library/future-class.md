---
title: "future 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::future"
dev_langs: 
  - "C++"
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# future 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an *asynchronous return object*.  
  
## 구문  
  
```  
template<class Ty>  
class future;  
```  
  
## 설명  
 Each standard *asynchronous provider* returns an object whose type is an instantiation of this template.  A `future` object provides the only access to the asynchronous provider that it is associated with.  If you need multiple asynchronous return objects that are associated with the same asynchronous provider, copy the `future` object to a [shared\_future](../standard-library/shared-future-class.md) object.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[future::future 생성자](../Topic/future::future%20Constructor.md)|`future` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[future::get 메서드](../Topic/future::get%20Method.md)|Retrieves the result that is stored in the associated asynchronous state.|  
|[future::share 메서드](../Topic/future::share%20Method.md)|Converts the object to a `shared_future`.|  
|[future::valid 메서드](../Topic/future::valid%20Method.md)|Specifies whether the object is not empty.|  
|[future::wait 메서드](../Topic/future::wait%20Method.md)|Blocks the current thread until the associated asynchronous state is ready.|  
|[future::wait\_for 메서드](../Topic/future::wait_for%20Method.md)|Blocks until the associated asynchronous state is ready or until the specified time has elapsed.|  
|[future::wait\_until 메서드](../Topic/future::wait_until%20Method.md)|Blocks until the associated asynchronous state is ready or until a specified point in time.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[future::operator\= 연산자](../Topic/future::operator=%20Operator.md)|Transfers the associated asynchronous state from a specified object.|  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)