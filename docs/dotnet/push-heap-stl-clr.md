---
title: "push_heap(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::push_heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push_heap 함수[STL/CLR]"
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# push_heap(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

범위내의 우선 요소들로 구성되어진 존재하는 힙에 범위의 끝에 있는 요소를 추가합니다.  
  
## 구문  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## 설명  
 이 함수는 STL 함수인 `push_heap`와 같은 작동을 합니다.  자세한 내용은 [push\_heap](../Topic/push_heap.md)을 참조하십시오.  
  
## 요구 사항  
 **헤더:**\<cliext\/algorithm\>  
  
 **네임스페이스:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)