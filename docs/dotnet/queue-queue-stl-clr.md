---
title: "queue::queue(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue 멤버[STL/CLR]"
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# queue::queue(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructs a container adapter object.  
  
## 구문  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### 매개 변수  
 right  
 Object to copy.  
  
 wrapped  
 Wrapped container to use.  
  
## 설명  
 The constructor:  
  
 `queue();`  
  
 creates an empty wrapped container.  You use it to specify an empty initial controlled sequence.  
  
 The constructor:  
  
 `queue(queue<Value, Container>% right);`  
  
 creates a wrapped container that is a copy of `right.get_container()`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the queue object `right`.  
  
 The constructor:  
  
 `queue(queue<Value, Container>^ right);`  
  
 creates a wrapped container that is a copy of `right->get_container()`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the queue object `*right`.  
  
 The constructor:  
  
 `explicit queue(container_type wrapped);`  
  
 uses the existing container `wrapped` as the wrapped container.  You use it to construct a queue from an existing container.  
  
## 예제  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **x x x x x**  
 **x x x x x**  
 **x x x x x**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)   
 [queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)