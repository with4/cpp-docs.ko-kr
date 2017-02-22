---
title: "&lt;typeindex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<typeindex>"
dev_langs: 
  - "C++"
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# &lt;typeindex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Include the standard header \<typeindex\> to define a class and function that support the indexing of objects of class [type\_info](../cpp/type-info-class.md).  
  
## 구문  
  
```cpp  
#include <typeindex>  
```  
  
## 설명  
 The [hash 구조체](../standard-library/hash-structure.md) defines a `hash function` that's suitable for mapping values of type [type\_index](../standard-library/type-index-class.md) to a distribution of index values.  
  
 The `type_index` class wraps a pointer to a `type_info` object to assist in indexing.  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)