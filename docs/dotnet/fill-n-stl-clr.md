---
title: "fill_n(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::fill_n"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fill_n 함수"
ms.assetid: bb9f2f71-ba1d-44ec-8b47-6ece149dd6b8
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# fill_n(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특정 요소로 시작하는 범위에서 지정된 요소 번호에 새 값을 할당합니다.  
  
## 구문  
  
```  
template<class _OutIt, class _Diff, class _Ty> inline  
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);  
```  
  
## 설명  
 This function behaves the same as the STL function `fill_n`.  자세한 내용은 [fill\_n](../Topic/fill_n.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)