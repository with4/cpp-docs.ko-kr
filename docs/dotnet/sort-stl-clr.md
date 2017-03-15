---
title: "sort(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sort 함수[STL/CLR]"
ms.assetid: e30f3e97-60c4-4a8e-89f1-75ec056f587a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# sort(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Arranges the elements in a specified range into a nondescending order or according to an ordering criterion specified by a binary predicate.  
  
## 구문  
  
```  
template<class _RanIt> inline  
    void sort(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `sort`.  자세한 내용은 [정렬](../Topic/sort.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)