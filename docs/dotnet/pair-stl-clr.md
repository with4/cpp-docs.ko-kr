---
title: "pair(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair 클래스[STL/CLR]"
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# pair(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that wraps a pair of values.  
  
## 구문  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### 매개 변수  
 Value1  
 The type of first wrapped value.  
  
 Value2  
 The type of second wrapped value.  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[pair::first\_type](../dotnet/pair-first-type-stl-clr.md)|The type of the first wrapped value.|  
|[pair::second\_type](../dotnet/pair-second-type-stl-clr.md)|The type of the second wrapped value.|  
  
|Member Object|설명|  
|-------------------|--------|  
|[pair::first](../dotnet/pair-first-stl-clr.md)|The first stored value.|  
|[pair::second](../dotnet/pair-second-stl-clr.md)|The second stored value.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[pair::pair](../dotnet/pair-pair-stl-clr.md)|Constructs a pair object.|  
|[pair::swap](../dotnet/pair-swap-stl-clr.md)|Swaps the contents of two pairs.|  
  
|연산자|설명|  
|---------|--------|  
|[pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)|Replaces the stored pair of values.|  
  
## 설명  
 The object stores a pair of values.  You use this template class to combine two values into a single object.  Note that `cliext::pair` \(described here\) stores only managed types; to store a pair of unmanaged types use `std::pair`, declared in `<utility>`.  
  
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [make\_pair](../dotnet/make-pair-stl-clr.md)