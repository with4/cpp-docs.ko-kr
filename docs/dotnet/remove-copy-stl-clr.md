---
title: "remove_copy(STL/CLR) | Microsoft Docs"
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
  - "cliext::remove_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy 함수[STL/CLR]"
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# remove_copy(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copies elements from a source range to a destination range, except that elements of a specified value are not copied, without disturbing the order of the remaining elements and returning the end of a new destination range.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## 설명  
 This function behaves the same as the STL function `remove_copy`.  자세한 내용은 [remove\_copy](../Topic/remove_copy.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)