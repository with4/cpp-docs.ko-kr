---
title: "copy(STL/CLR) | Microsoft Docs"
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
  - "cliext::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copy 함수[STL/CLR]"
ms.assetid: f6738535-fde6-446e-a797-bf2b457c2bff
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# copy(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assigns the values of elements from a source range to a destination range, iterating through the source sequence of elements and assigning them new positions in a forward direction.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
```  
  
## 설명  
 This function behaves the same as the STL function `copy`.  자세한 내용은 [copy](../Topic/copy.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)