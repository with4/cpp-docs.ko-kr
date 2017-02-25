---
title: "deque::generic_reverse_iterator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::generic_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_reverse_iterator 멤버[STL/CLR]"
ms.assetid: e2a837bc-24be-4a99-a0ee-9dc73be97955
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# deque::generic_reverse_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The type of a reverse iterator for use with the generic interface for the container.  
  
## 구문  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;  
```  
  
## 설명  
 The type describes a generic reverse iterator that can be used with the generic interface for this template container class.  
  
## 예제  
  
```  
// cliext_deque_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a c c**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::generic\_container](../dotnet/deque-generic-container-stl-clr.md)   
 [deque::generic\_value](../dotnet/deque-generic-value-stl-clr.md)