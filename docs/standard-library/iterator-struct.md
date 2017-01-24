---
title: "iterator 구조체 | Microsoft Docs"
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
  - "iterator"
  - "std::iterator"
  - "std.iterator"
  - "xutility/std::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator 클래스"
  - "iterator 구조체"
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iterator 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An empty base struct used to ensure that a user\-defined iterator class works properly with **iterator\_trait**s.  
  
## 구문  
  
```  
template<class Category, class Type, class Distance = ptrdiff_t  
    class Pointer = Type*, class Reference = Type&>  
    struct iterator {  
        typedef Category iterator_category;  
        typedef Type value_type;  
        typedef Distance difference_type;  
        typedef Distance distance_type;  
        typedef Pointer pointer;  
        typedef Reference reference;  
    };  
```  
  
## 설명  
 The template struct serves as a base type for all iterators.  It defines the member types  
  
-   `iterator_category` \(a synonym for the template parameter `Category`\).  
  
-   `value_type` \(a synonym for the template parameter **Type**\).  
  
-   `difference_type` \(a synonym for the template parameter `Distance`\).  
  
-   `distance_type` \(a synonym for the template parameter `Distance`\)  
  
-   `pointer` \(a synonym for the template parameter `Pointer`\).  
  
-   `reference` \(a synonym for the template parameter `Reference`\).  
  
 Note that `value_type` should not be a constant type even if **pointer** points at an object of const **Type** and reference designates an object of const **Type**.  
  
## 예제  
 See [iterator\_traits](../standard-library/iterator-traits-struct.md) for an example of how to declare and use the types in the iterator base class.  
  
## 요구 사항  
 **Header:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)