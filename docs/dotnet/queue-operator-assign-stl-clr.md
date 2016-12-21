---
title: "queue::operator=(STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 멤버[STL/CLR]"
ms.assetid: 826c335a-5680-498c-b57d-e7bc93a914be
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::operator=(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Replaces the controlled sequence.  
  
## 구문  
  
```  
queue <Value, Container>% operator=(queue <Value, Container>% right);  
```  
  
#### 매개 변수  
 right  
 Container adapter to copy.  
  
## 설명  
 The member operator copies `right` to the object, then returns `*this`.  You use it to replace the controlled sequence with a copy of the controlled sequence in `right`.  
  
## 예제  
  
```  
// cliext_queue_operator_as.cpp   
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
  
// assign to a new container   
    Myqueue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)