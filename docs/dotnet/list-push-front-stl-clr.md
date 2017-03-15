---
title: "list::push_front(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::push_front"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push_front 멤버[STL/CLR]"
ms.assetid: 47525641-1139-44fc-ac62-bdc04876d9e0
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::push_front(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Adds a new first element.  
  
## 구문  
  
```  
void push_front(value_type val);  
```  
  
## 설명  
 The member function inserts an element with value `val` at the beginning of the controlled sequence.  You use it to prepend another element to the list.  
  
## 예제  
  
```  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::pop\_back](../dotnet/list-pop-back-stl-clr.md)   
 [list::pop\_front](../dotnet/list-pop-front-stl-clr.md)   
 [list::push\_back](../dotnet/list-push-back-stl-clr.md)