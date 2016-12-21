---
title: "inplace_merge(STL/CLR) | Microsoft Docs"
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
  - "cliext::inplace_merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inplace_merge 함수[STL/CLR]"
ms.assetid: e6948c03-8c5b-4a7c-915c-0a531946a321
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# inplace_merge(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Combines the elements from two consecutive sorted ranges into a single sorted range, where the ordering criterion may be specified by a binary predicate.  
  
## 구문  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `inplace_merge` For more information, see [inplace\_merge](../Topic/inplace_merge.md).  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)