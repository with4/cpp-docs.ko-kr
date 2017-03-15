---
title: "stable_partition(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stable_partition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stable_partition 함수[STL/CLR]"
ms.assetid: b82c194c-ae38-4afb-b255-a95a4c2b3101
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# stable_partition(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classifies elements in a range into two disjoint sets, with those elements satisfying a unary predicate preceding those that fail to satisfy it, preserving the relative order of equivalent elements.  
  
## 구문  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `stable_partition`.  자세한 내용은 [stable\_partition](../Topic/stable_partition.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)