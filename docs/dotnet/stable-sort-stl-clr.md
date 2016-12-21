---
title: "stable_sort(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stable_sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stable_sort 함수[STL/CLR]"
ms.assetid: c28fc2df-c68b-4923-ac16-9f8edd926fbb
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stable_sort(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Arranges the elements in a specified range into a nondescending order or according to an ordering criterion specified by a binary predicate and preserves the relative ordering of equivalent elements.  
  
## 구문  
  
```  
template<class _BidIt> inline  
    void stable_sort(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `stable_sort`.  자세한 내용은 [stable\_sort](../Topic/stable_sort.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)