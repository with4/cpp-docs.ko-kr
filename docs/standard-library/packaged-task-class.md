---
title: "packaged_task 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::packaged_task"
dev_langs: 
  - "C++"
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# packaged_task 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an *asynchronous provider* that is a call wrapper whose call signature is `Ty(ArgTypes...)`.  Its *associated asynchronous state* holds a copy of its callable object in addition to the potential result.  
  
## 구문  
  
```  
template<class>  
class packaged_task;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[packaged\_task::packaged\_task 생성자](../Topic/packaged_task::packaged_task%20Constructor.md)|`packaged_task` 개체를 생성합니다.|  
|[packaged\_task::~packaged\_task 소멸자](../Topic/packaged_task::~packaged_task%20Destructor.md)|`packaged_task` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[packaged\_task::get\_future 메서드](../Topic/packaged_task::get_future%20Method.md)|Returns a [future](../standard-library/future-class.md) object that has the same associated asynchronous state.|  
|[packaged\_task::make\_ready\_at\_thread\_exit 메서드](../Topic/packaged_task::make_ready_at_thread_exit%20Method.md)|Calls the callable object that's stored in the associated asynchronous state and atomically stores the returned value.|  
|[packaged\_task::reset 메서드](../Topic/packaged_task::reset%20Method.md)|Replaces the associated asynchronous state.|  
|[packaged\_task::swap 메서드](../Topic/packaged_task::swap%20Method.md)|Exchanges the associated asynchronous state with that of a specified object.|  
|[packaged\_task::valid 메서드](../Topic/packaged_task::valid%20Method.md)|Specifies whether the object has an associated asynchronous state.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[packaged\_task::operator\= 연산자](../Topic/packaged_task::operator=%20Operator.md)|Transfers an associated asynchronous state from a specified object.|  
|[packaged\_task::operator\(\) 연산자](../Topic/packaged_task::operator\(\)%20Operator.md)|Calls the callable object that's stored in the associated asynchronous state, atomically stores the returned value, and sets the state to *ready*.|  
|[packaged\_task::operator bool 연산자](../Topic/packaged_task::operator%20bool%20Operator.md)|Specifies whether the object has an associated asynchronous state.|  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)