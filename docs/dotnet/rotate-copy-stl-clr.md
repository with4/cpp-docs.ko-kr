---
title: "rotate_copy(STL/CLR) | Microsoft Docs"
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
  - "cliext::rotate_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rotate_copy 함수[STL/CLR]"
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# rotate_copy(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exchanges the elements in two adjacent ranges within a source range and copies the result to a destination range.  
  
## 구문  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## 설명  
 This function behaves the same as the STL function `rotate_copy`.  자세한 내용은 [rotate\_copy](../Topic/rotate_copy.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)