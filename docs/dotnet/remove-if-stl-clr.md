---
title: "remove_if(STL/CLR) | Microsoft Docs"
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
  - "cliext::remove_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_if 함수[STL/CLR]"
ms.assetid: de501d3f-965b-4a99-b833-f6fa303fbcdc
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# remove_if(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eliminates elements that satisfy a predicate from a given range without disturbing the order of the remaining elements and returning the end of a new range free of the specified value.  
  
## 구문  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `remove_if`.  자세한 내용은 [remove\_if](../Topic/remove_if.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)