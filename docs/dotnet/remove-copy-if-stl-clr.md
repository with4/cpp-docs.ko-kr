---
title: "remove_copy_if(STL/CLR) | Microsoft Docs"
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
  - "cliext::remove_copy_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy_if 함수[STL/CLR]"
ms.assetid: 5307f5fe-b6bb-4968-8da1-fea84ab96655
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# remove_copy_if(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copies elements from a source range to a destination range, except that satisfying a predicate are not copied, without disturbing the order of the remaining elements and returning the end of a new destination range.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `remove_copy_if`.  자세한 내용은 [remove\_copy\_if](../Topic/remove_copy_if.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)