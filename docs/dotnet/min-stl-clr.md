---
title: "min(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::min"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "min 함수[STL/CLR]"
ms.assetid: 7a2c82d1-424c-48a9-a944-adcf95511aef
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# min(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 개체를 비교하고 이진 예측에 의해 정렬 기준이 지정된 곳의 둘 중에서 더 작은 값을 반환합니다.  
  
## 구문  
  
```  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## 설명  
 This function behaves the same as the STL function `min`.  자세한 내용은 [분](../Topic/min.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)