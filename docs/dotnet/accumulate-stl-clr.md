---
title: "accumulate(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::accumulate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accumulate 함수[STL/CLR]"
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# accumulate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Computes the sum of all the elements in a specified range including some initial value by computing successive partial sums or computes the result of successive partial results similarly obtained from using a specified binary operation other than the sum.  
  
## 구문  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## 설명  
 This function behaves the same as the STL numeric function `accumulate`.  자세한 내용은 [accumulate](../Topic/accumulate.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/numeric\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [numeric](../dotnet/numeric-stl-clr.md)