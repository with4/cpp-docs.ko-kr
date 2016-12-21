---
title: "inner_product(STL/CLR) | Microsoft Docs"
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
  - "cliext::inner_product"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inner_product 함수[STL/CLR]"
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# inner_product(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Computes the sum of the element\-wise product of two ranges and adds it to a specified initial value or computes the result of a generalized procedure where the sum and product binary operations are replaced by other specified binary operations.  
  
## 구문  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## 설명  
 This function behaves the same as the STL numeric function `inner_product`.  자세한 내용은 [inner\_product](../Topic/inner_product.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/numeric\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [numeric](../dotnet/numeric-stl-clr.md)