---
title: "list::resize(STL/CLR) | Microsoft Docs"
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
  - "cliext::list::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize 멤버[STL/CLR]"
ms.assetid: c4b8d41f-a62b-4dbc-8568-0e0a9da24016
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::resize(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소 수를 변경합니다.  
  
## 구문  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### 매개 변수  
 new\_size  
 New size of the controlled sequence.  
  
 val  
 Value of the padding element.  
  
## 설명  
 The member functions both ensure that [list::size](../dotnet/list-size-stl-clr.md)`()` henceforth returns `new_size`.  If it must make the controlled sequence longer, the first member function appends elements with value `value_type()`, while the second member function appends elements with value `val`.  To make the controlled sequence shorter, both member functions effectively erase the last element [list::size](../dotnet/list-size-stl-clr.md)`() -` `new_size` times.  You use it to ensure that the controlled sequence has size `new_size`, by either trimming or padding the current controlled sequence.  
  
## 예제  
  
```  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **x x x x x**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)   
 [list::erase](../dotnet/list-erase-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)