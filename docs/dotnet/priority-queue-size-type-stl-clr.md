---
title: "priority_queue::size_type(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type 멤버[STL/CLR]"
ms.assetid: 0f38e670-4f61-474a-990c-0b8cd31ada5e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# priority_queue::size_type(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
## 구문  
  
```  
typedef int size_type;  
```  
  
## 설명  
 형식은 음이 아닌 요소 수를 설명합니다.  
  
## 예제  
  
```  
// cliext_priority_queue_size_type.cpp   
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
  
// compute positive difference   
    Mypriority_queue::size_type diff = c1.size();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("size difference = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **c a b**  
**size difference \= 2**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)