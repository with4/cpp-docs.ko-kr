---
title: "max_element(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::max_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_element 함수[STL/CLR]"
ms.assetid: c6274bae-1216-4285-b395-254280253dae
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# max_element(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 된 범위에서 가장 큰 요소의 첫 번째 항목을 찾습니다. 여기서 이진 술부에 의해 정렬 기준을 지정할 수 있습니다.  
  
## 구문  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `max_element`.  자세한 내용은 [max\_element](../Topic/max_element.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)