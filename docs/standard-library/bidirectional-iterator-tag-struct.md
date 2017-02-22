---
title: "bidirectional_iterator_tag 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xutility/std::bidirectional_iterator_tag"
  - "std::bidirectional_iterator_tag"
  - "std.bidirectional_iterator_tag"
  - "bidirectional_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bidirectional_iterator_tag 클래스"
  - "bidirectional_iterator_tag 구조체"
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bidirectional_iterator_tag 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A class that provides a return type for **iterator\_category** function that represents a bidirectional iterator.  
  
## 구문  
  
```  
  
   struct bidirectional_iterator_tag  
: public forward_iterator_tag {};  
```  
  
## 설명  
 The category tag classes are used as compile tags for algorithm selection.  The template function needs to find the most specific category of its iterator argument, so that it can use the most efficient algorithm at compile time.  For every iterator of type `Iterator`, `iterator_traits`\<`Iterator`\>::**iterator\_category** must be defined to be the most specific category tag that describes the iterator's behavior.  
  
 The type is the same as **iterator**\<**Iter**\>::**iterator\_category** when **Iter** describes an object that can serve as a bidirectional iterator.  
  
## 예제  
 See [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) for an example of how to use `bidirectional_iterator_tag`.  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [forward\_iterator\_tag 구조체](../standard-library/forward-iterator-tag-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)