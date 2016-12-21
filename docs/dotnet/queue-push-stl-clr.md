---
title: "queue::push(STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::push"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push 멤버[STL/CLR]"
ms.assetid: 97cf1f98-d4c4-417f-b57a-89cdd351ef65
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::push(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Adds a new last element.  
  
## 구문  
  
```  
void push(value_type val);  
```  
  
## 설명  
 The member function adds an element with value `val` at the end of the queue.  You use it to append an element to the queue.  
  
## 예제  
  
```  
// cliext_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::pop](../dotnet/queue-pop-stl-clr.md)