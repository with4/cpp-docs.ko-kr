---
title: "set_difference(STL/CLR) | Microsoft Docs"
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
  - "cliext::set_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set_difference 함수[STL/CLR]"
ms.assetid: 47a34d92-53d7-4065-9302-9e2e70e46c4d
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set_difference(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unites all of the elements that belong to one sorted source range, but not to a second sorted source range, into a single, sorted destination range, where the ordering criterion may be specified by a binary predicate.  
  
## 구문  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `set_difference`.  자세한 내용은 [set\_difference](../Topic/set_difference.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)