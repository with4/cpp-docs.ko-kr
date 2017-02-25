---
title: "fill(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::fill"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fill 함수"
ms.assetid: eb67241c-9bb3-497e-bec6-639900c60758
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# fill(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assigns the same new value to every element in a specified range.  
  
## 구문  
  
```  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## 설명  
 This function behaves the same as the STL function `fill`.  자세한 내용은 [채우기](../Topic/fill.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)