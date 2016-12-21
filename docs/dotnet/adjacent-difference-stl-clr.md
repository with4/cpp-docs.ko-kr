---
title: "adjacent_difference(STL/CLR) | Microsoft Docs"
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
  - "cliext::adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_difference 함수"
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# adjacent_difference(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

입력 범위의 각 요소 및 그 이전의 연속적인 차이를 계산하고, 대상 범위에 결과를 출력 또는 차분 연산이 서로에 의해 대체되는 일반화 된 절차, 지정된 이진 연산 결과를 연산합니다.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## 설명  
 이 함수는 STI 숫자 함수 `adjacent_difference`와 같이 작동합니다.  자세한 내용은 [adjacent\_difference](../Topic/adjacent_difference.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/numeric\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [numeric](../dotnet/numeric-stl-clr.md)