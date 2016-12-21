---
title: "once_flag 구조체 | Microsoft Docs"
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
  - "mutex/std::once_flag"
dev_langs: 
  - "C++"
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# once_flag 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a `struct` that is used with the template function [call\_once](../Topic/call_once%20Function.md) to ensure that initialization code is called only once, even in the presence of multiple threads of execution.  
  
## 구문  
  
```cpp  
struct once_flag  
{  
   constexpr once_flag() noexcept;  
   once_flag(const once_flag&);  
   once_flag& operator=(const once_flag&);  
};  
```  
  
## 설명  
 The `once_flag` `struct` has only a default constructor.  
  
 Objects of type `once_flag` can be created, but they cannot be copied.  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)