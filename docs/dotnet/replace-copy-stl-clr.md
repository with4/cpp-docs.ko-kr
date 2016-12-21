---
title: "replace_copy(STL/CLR) | Microsoft Docs"
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
  - "cliext::replace_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "replace_copy 함수[STL/CLR]"
ms.assetid: b531b49b-b16d-4b04-8f80-74f43dd496a4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# replace_copy(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Examines each element in a source range and replaces it if it matches a specified value while copying the result into a new destination range.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
## 설명  
 This function behaves the same as the STL function `replace_copy`.  자세한 내용은 [replace\_copy](../Topic/replace_copy.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)