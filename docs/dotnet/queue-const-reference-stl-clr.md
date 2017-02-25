---
title: "queue::const_reference(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::const_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reference 멤버[STL/CLR]"
ms.assetid: e2398b75-e072-4769-82df-f2607e29c6e4
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# queue::const_reference(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소에 대한 상수 참조의 형식입니다.  
  
## 구문  
  
```  
typedef value_type% const_reference;  
```  
  
## 설명  
 The type describes a constant reference to an element.  
  
## 예제  
  
```  
// cliext_queue_const_reference.cpp   
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
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Myqueue::const_reference cref = c1.front();   
        System::Console::Write(" {0}", cref);   
        }   
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
 [queue::reference](../dotnet/queue-reference-stl-clr.md)   
 [queue::value\_type](../dotnet/queue-value-type-stl-clr.md)