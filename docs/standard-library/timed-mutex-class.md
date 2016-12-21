---
title: "timed_mutex 클래스 | Microsoft Docs"
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
  - "mutex/std::timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# timed_mutex 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a *timed mutex type*.  Objects of this type are used to enforce mutual exclusion through time\-limited blocking within a program.  
  
## 구문  
  
```  
class timed_mutex;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[timed\_mutex::timed\_mutex 생성자](../Topic/timed_mutex::timed_mutex%20Constructor.md)|Constructs a `timed_mutex` object that's not locked.|  
|[timed\_mutex::~timed\_mutex 소멸자](../Topic/timed_mutex::~timed_mutex%20Destructor.md)|Releases any resources that are used by the `timed_mutex` object.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[timed\_mutex::lock 메서드](../Topic/timed_mutex::lock%20Method.md)|스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|  
|[timed\_mutex::try\_lock 메서드](../Topic/timed_mutex::try_lock%20Method.md)|차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[timed\_mutex::try\_lock\_for 메서드](../Topic/timed_mutex::try_lock_for%20Method.md)|Attempts to obtain ownership of the `mutex` for a specified time interval.|  
|[timed\_mutex::try\_lock\_until 메서드](../Topic/timed_mutex::try_lock_until%20Method.md)|Attempts to obtain ownership of the `mutex` until a specified time.|  
|[timed\_mutex::unlock 메서드](../Topic/timed_mutex::unlock%20Method.md)|`mutex`의 소유권을 해제합니다.|  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)