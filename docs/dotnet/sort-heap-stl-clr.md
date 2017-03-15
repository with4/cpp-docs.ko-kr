---
title: "sort_heap(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::sort_heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sort_heap 함수[STL/CLR]"
ms.assetid: a8fa6b76-90cd-413b-9c5b-f65b93d4bbed
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# sort_heap(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Converts a heap into a sorted range.  
  
## 구문  
  
```  
template<class _RanIt> inline  
    void sort_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `sort_heap`.  자세한 내용은 [sort\_heap](../Topic/sort_heap.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)