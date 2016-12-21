---
title: "allocator&lt;void&gt; 클래스 | Microsoft Docs"
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
  - "memory/std::allocator<void>"
  - "std::allocator<void>"
  - "std.allocator<void>"
  - "allocator<void>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator<void> 클래스"
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator&lt;void&gt; 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A specialization of the template class allocator to type `void`, defining the types that make sense in this context.  
  
## 구문  
  
```  
template<>  
   class allocator<void> {  
   typedef void *pointer;  
   typedef const void *const_pointer;  
   typedef void value_type;  
   template<class Other>  
      struct rebind;  
   allocator( );  
   allocator(  
      const allocator<void>&  
   );  
   template<class Other>  
      allocator(  
         const allocator<Other>&  
      );  
   template<class Other>  
      allocator<void>& operator=(  
         const allocator<Other>&  
      );  
   };  
```  
  
## 설명  
 The class explicitly specializes template class [allocator](../standard-library/allocator-class.md) for type *void.* Its constructors and assignment operator behave the same as for the template class, but it defines only the following types:  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md).  
  
-   [pointer](../Topic/allocator::pointer.md).  
  
-   [value\_type](../Topic/allocator::value_type.md).  
  
-   [rebind](../Topic/allocator::rebind.md), a nested template class.  
  
## 요구 사항  
 **Header:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)