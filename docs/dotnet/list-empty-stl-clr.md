---
title: "list::empty(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "empty 멤버[STL/CLR]"
ms.assetid: f45edf8a-927d-41ff-9c09-cb0fba4f08b8
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::empty(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests whether no elements are present.  
  
## 구문  
  
```  
bool empty();  
```  
  
## 설명  
 The member function returns true for an empty controlled sequence.  It is equivalent to [list::size](../dotnet/list-size-stl-clr.md)`() == 0`.  You use it to test whether the list is empty.  
  
## 예제  
  
```  
// cliext_list_empty.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
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
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::size](../dotnet/list-size-stl-clr.md)