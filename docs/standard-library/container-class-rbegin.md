---
title: "Container Class::rbegin | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin 메서드"
ms.assetid: c1f0d60c-93aa-4313-81b9-04e3f9c796c2
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Container Class::rbegin
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  This topic is in the Visual C\+\+ documentation as a nonfunctional example of containers used in the Standard C\+\+ Library.  For more information, see [STL Containers](../standard-library/stl-containers.md).  
  
 Returns a reverse iterator that points just beyond the end of the controlled sequence, designating the beginning of the reverse sequence.  
  
## 구문  
  
```  
const_reverse_iterator rbegin( ) const;  
reverse_iterator rbegin( );  
```  
  
## 참고 항목  
 [Sample Container 클래스](../standard-library/sample-container-class.md)