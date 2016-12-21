---
title: "includes(STL/CLR) | Microsoft Docs"
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
  - "cliext::includes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includes 함수[STL/CLR]"
ms.assetid: 566307f4-92e0-4acc-ba49-caa48f3ec744
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# includes(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests whether one sorted range contains all the elements contained in a second sorted range, where the ordering or equivalence criterion between elements may be specified by a binary predicate.  
  
## 구문  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `includes`.  자세한 내용은 [includes](../Topic/includes.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)