---
title: "equal_range(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range 함수[STL/CLR]"
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# equal_range(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정렬된 범위에서 한쌍의 위치를 검색하고, 첫번째로 지정된 요소의 위치보다 더 적거나 같은 것을 찾고, 두번째로 요소의 위치보다 더 큰것을 찾으며, 동등한 양식 또는 순서에서 위치를 설정하기위해 사용되는 순서가 이진 술어로써 지정될 수 있습니다.  
  
## 구문  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## 설명  
 이 함수는 STI 함수 `equal_range`와 같이 작동합니다.  자세한 내용은 [equal\_range](../Topic/equal_range.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)