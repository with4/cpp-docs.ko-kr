---
title: "recursive_mutex 클래스 | Microsoft Docs"
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
  - "mutex/std::recursive_mutex"
dev_langs: 
  - "C++"
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# recursive_mutex 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*mutex type* 을 나타냅니다.  In contrast to [mutex](../standard-library/mutex-class-stl.md), the behavior of calls to locking methods for objects that are already locked is well\-defined.  
  
## 구문  
  
```  
class recursive_mutex;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[recursive\_mutex::recursive\_mutex 생성자](../Topic/recursive_mutex::recursive_mutex%20Constructor.md)|`recursive_mutex` 개체를 생성합니다.|  
|[recursive\_mutex::~recursive\_mutex 소멸자](../Topic/recursive_mutex::~recursive_mutex%20Destructor.md)|Releases any resources that are used by the `recursive_mutex` object.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[recursive\_mutex::lock 메서드](../Topic/recursive_mutex::lock%20Method.md)|Blocks the calling thread until the thread obtains ownership of the mutex.|  
|[recursive\_mutex::try\_lock 메서드](../Topic/recursive_mutex::try_lock%20Method.md)|Attempts to obtain ownership of the mutex without blocking.|  
|[recursive\_mutex::unlock 메서드](../Topic/recursive_mutex::unlock%20Method.md)|Releases ownership of the mutex.|  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)