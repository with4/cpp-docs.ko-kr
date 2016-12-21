---
title: "operator== (pair)(STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator== 멤버[STL/CLR]"
ms.assetid: 2b4879a1-f326-4fb3-b113-bd8d457f9802
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator== (pair)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

쌍 비교와 동일합니다.  
  
## 구문  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### 매개 변수  
 left  
 비교 왼쪽 쌍입니다.  
  
 right  
 비교 오른쪽 쌍입니다.  
  
## 설명  
 연산자 함수는 `left``.first ==` `right``.first &&` `left``.second ==` `right``.second`을 반환합니다.   두 쌍의 요소에서 요소를 비교할 때  `left` 가  `right` 와 순서가 같은지 여부의 테스트에 사용합니다.  
  
## 예제  
  
```  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[x, 4\]**  
**\[x 3\] \=\= \[x 3\] 은  True 입니다.**  
**\[x 3\] \=\= \[x 4\] 은 False입니다.**   
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [pair](../dotnet/pair-stl-clr.md)   
 [operator\!\= \(pair\)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [operator\< \(pair\)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator\>\= \(pair\)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator\> \(pair\)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator\<\= \(pair\)](../dotnet/operator-less-or-equal-pair-stl-clr.md)