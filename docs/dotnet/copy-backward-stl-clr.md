---
title: "copy_backward(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::copy_backward"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copy_backward 함수[STL/CLR]"
ms.assetid: 649db3fd-5a79-44b6-bea9-ecbcbeba1f32
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# copy_backward(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

소스 시퀀스의 요소를 반복하고 뒤쪽으로의 새 위치를 지정하는 대상 범위를 소스 범위에서 요소 값을 할당 합니다.  
  
## 구문  
  
```  
template<class _BidIt1, class _BidIt2> inline  
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,  
        _BidIt2 _Dest);  
```  
  
## 설명  
 This function behaves the same as the STL function `copy_backward`.  자세한 내용은 [copy\_backward](../Topic/copy_backward.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)