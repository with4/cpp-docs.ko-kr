---
title: "Container Class::reference | Microsoft Docs"
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
  - "reference 메서드"
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Container Class::reference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  This topic is in the Visual C\+\+ documentation as a nonfunctional example of containers used in the Standard C\+\+ Library.  For more information, see [STL Containers](../standard-library/stl-containers.md).  
  
 Describes an object that can serve as a reference to an element of the controlled sequence.  
  
## 구문  
  
```  
  
typedef T2 reference;  
  
```  
  
## 설명  
 It is described here as a synonym for the unspecified type **T2** \(typically **Alloc::reference**\).  An object of type **reference** can be cast to an object of type [const\_reference](../standard-library/container-class-const-reference.md).  
  
## 참고 항목  
 [Sample Container 클래스](../standard-library/sample-container-class.md)