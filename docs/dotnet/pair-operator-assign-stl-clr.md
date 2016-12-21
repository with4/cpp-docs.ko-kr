---
title: "pair::operator=(STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 멤버[STL/CLR]"
ms.assetid: b6228037-914e-4efa-8491-65dbb0e93f61
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::operator=(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Replaces the stored pair of values.  
  
## 구문  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### 매개 변수  
 right  
 Pair to copy.  
  
## 설명  
 The member operator copies `right` to the object, then returns `*this`.  You use it to replace the stored pair of values with a copy of the stored pair of values in `right`.  
  
## 예제  
  
```  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[x, 3\]**   
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [pair](../dotnet/pair-stl-clr.md)