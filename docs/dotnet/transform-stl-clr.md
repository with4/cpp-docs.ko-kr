---
title: "transform(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::transform"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "변환 함수[STL/CLR]"
ms.assetid: 08940969-6d10-40e4-a35b-68dd801b3949
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# transform(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 소스 범위에서 요소 쌍에 또는 소스 범위에 있는 각 요소에 지정된 함수 개체를 적용하고, 동시에 대상 범위에 수평으로 함수 개체의 반환 값을 복사합니다.  
  
## 구문  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## 설명  
 이 함수는 STI 함수 `transform`와 같이 작동합니다.  자세한 내용은 [transform](../Topic/transform.md)을 참조하십시오.  
  
## 요구 사항  
 **Header:** \<cliext\/algorithm\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [algorithm](../dotnet/algorithm-stl-clr.md)