---
title: "forward_iterator_tag 구조체 | Microsoft Docs"
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
  - "std.forward_iterator_tag"
  - "forward_iterator_tag"
  - "std::forward_iterator_tag"
  - "xutility/std::forward_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_iterator_tag 클래스"
  - "forward_iterator_tag 구조체"
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# forward_iterator_tag 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A class that provides a return type for **iterator\_category** function that represents a forward iterator.  
  
## 구문  
  
```  
  
   struct forward_iterator_tag  
: public input_iterator_tag {};  
```  
  
## 설명  
 The category tag classes are used as compile tags for algorithm selection.  The template function needs to find out what is the most specific category of its iterator argument so that it can use the most efficient algorithm at compile time.  For every iterator of type `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** must be defined to be the most specific category tag that describes the iterator's behavior.  
  
 The type is the same as **iterator**\<**Iter**\>**::iterator\_category** when **Iter** describes an object that can serve as a forward iterator.  
  
## 예제  
 See [iterator\_traits](../standard-library/iterator-traits-struct.md) or [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) for an example of how to use the **iterator\_tag**s.  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [input\_iterator\_tag 구조체](../standard-library/input-iterator-tag-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)