---
title: "priority_queue::top(STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue::top"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "top 멤버[STL/CLR]"
ms.assetid: e45211d5-e6df-4c03-97fd-57afb87af58c
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::top(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accesses the highest\-priority element.  
  
## 구문  
  
```  
reference top();  
```  
  
## 설명  
 The member function returns a reference to the top \(highest\-priority\) element of the controlled sequence, which must be non\-empty.  You use it to access the highest\-priority element, when you know it exists.  
  
## 예제  
  
```  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c a b**  
**top\(\) \= c**  
 **x a b**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::top\_item](../dotnet/priority-queue-top-item-stl-clr.md)