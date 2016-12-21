---
title: "pair::first(STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::first"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "first 멤버[STL/CLR]"
ms.assetid: 0dd2278f-adf9-46df-8ac8-7e8e1a2ef52e
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::first(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

첫 번째 래퍼된 값입니다.  
  
## 구문  
  
```  
Value1 first;  
```  
  
## 설명  
 개체는 첫 번째 래퍼된 값을 저장합니다.  
  
## 예제  
  
```  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**   
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [pair](../dotnet/pair-stl-clr.md)   
 [pair::first\_type](../dotnet/pair-first-type-stl-clr.md)   
 [pair::second](../dotnet/pair-second-stl-clr.md)   
 [pair::second\_type](../dotnet/pair-second-type-stl-clr.md)