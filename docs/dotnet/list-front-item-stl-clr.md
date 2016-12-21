---
title: "list::front_item(STL/CLR) | Microsoft Docs"
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
  - "cliext::list::front_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_item 멤버[STL/CLR]"
ms.assetid: c871873b-7745-442b-9760-9d8096fa8610
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::front_item(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accesses the first element.  
  
## 구문  
  
```  
property value_type front_item;  
```  
  
## 설명  
 The property accesses the first element of the controlled sequence, which must be non\-empty.  You use it to read or write the first element, when you know it exists.  
  
## 예제  
  
```  
// cliext_list_front_item.cpp   
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
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**front\_item \= a**  
 **x b c**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::back](../dotnet/list-back-stl-clr.md)   
 [list::back\_item](../dotnet/list-back-item-stl-clr.md)   
 [list::front](../dotnet/list-front-stl-clr.md)