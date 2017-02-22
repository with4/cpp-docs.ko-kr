---
title: "Container Class::swap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap 메서드"
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Container Class::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  This topic is in the Visual C\+\+ documentation as a nonfunctional example of containers used in the Standard C\+\+ Library.  For more information, see [STL Containers](../standard-library/stl-containers.md).  
  
 Swaps the controlled sequences between **\*this** and `_Right`.  
  
## 구문  
  
```  
  
      void swap(  
   Container& _Right  
);  
```  
  
## 설명  
 If **get\_allocator \=\=** `_Right`**.get\_allocator**, it does so in constant time.  Otherwise, it performs a number of element assignments and constructor calls proportional to the number of elements in the two controlled sequences.  
  
## 참고 항목  
 [Sample Container 클래스](../standard-library/sample-container-class.md)