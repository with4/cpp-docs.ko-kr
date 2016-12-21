---
title: "count(STL/CLR) | Microsoft Docs"
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
  - "cliext::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count 함수[STL/CLR]"
ms.assetid: 6d10abb4-3c48-469c-804c-281015b12865
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# count(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Returns the number of elements in a range whose values match a specified value.  
  
## 구문  
  
```  
template<class _InIt, class _Ty> inline  
    typename iterator_traits<_InIt>::difference_type  
        count(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
## 설명  
 This function behaves the same as the STL function `count`.  자세한 내용은 [count](../Topic/count.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)