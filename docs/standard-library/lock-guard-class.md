---
title: "lock_guard 클래스 | Microsoft Docs"
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
  - "mutex/std::lock_guard"
dev_langs: 
  - "C++"
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lock_guard 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a template that can be instantiated to create an object whose destructor unlocks a `mutex`.  
  
## 구문  
  
```  
template<class Mutex>  
class lock_guard;  
```  
  
## 설명  
 The template argument `Mutex` must name a *mutex type*.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`lock_guard::mutex_type`|Synonym for the template argument `Mutex`.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[lock\_guard::lock\_guard 생성자](../Topic/lock_guard::lock_guard%20Constructor.md)|`lock_guard` 개체를 생성합니다.|  
|[lock\_guard::~lock\_guard 소멸자](../Topic/lock_guard::~lock_guard%20Destructor.md)|Unlocks the `mutex` that was passed to the constructor.|  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)