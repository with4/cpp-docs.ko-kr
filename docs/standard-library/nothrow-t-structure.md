---
title: "nothrow_t 구조체 | Microsoft Docs"
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
  - "nothrow_t"
  - "std.nothrow_t"
  - "std::nothrow_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nothrow_t 클래스"
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nothrow_t 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The struct is used as a function parameter to operator new to indicate that the function should return a null pointer to report an allocation failure, rather than throw an exception.  
  
## 구문  
  
```  
struct std::nothrow_t {};  
```  
  
## 설명  
 The struct helps the compiler to select the correct version of the constructor.  [nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md) is a synonym for objects of type `std::nothrow_t`.  
  
## 예제  
 See [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) and [operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) for examples of how `std::nothrow_t` is used as a function parameter.  
  
## 요구 사항  
 **Header:** \<new\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)