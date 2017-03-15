---
title: "find_if(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::find_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find_if 함수[STL/CLR]"
ms.assetid: fd0db2be-a1e1-417e-8eea-653b08c9577e
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# find_if(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Locates the position of the first occurrence of an element in a range that satisfies a specified condition.  
  
## 구문  
  
```  
template<class _InIt, class _Pr> inline  
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `find_if`.  자세한 내용은 [find\_if](../Topic/find_if.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)