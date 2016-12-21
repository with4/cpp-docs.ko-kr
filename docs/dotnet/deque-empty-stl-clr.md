---
title: "deque::empty(STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "empty 멤버[STL/CLR]"
ms.assetid: 6ff3dd07-ebdf-47f9-b0d2-8a3229390d3b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::empty(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests whether no elements are present.  
  
## 구문  
  
```  
bool empty();  
```  
  
## 설명  
 The member function returns true for an empty controlled sequence.  It is equivalent to [deque::size](../dotnet/deque-size-stl-clr.md)`() == 0`.  You use it to test whether the deque is empty.  
  
## 예제  
  
```  
// cliext_deque_empty.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3**  
**empty\(\) \= False**  
**size\(\) \= 0**  
**empty\(\) \= True**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::size](../dotnet/deque-size-stl-clr.md)