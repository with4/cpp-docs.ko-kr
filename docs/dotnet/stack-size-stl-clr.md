---
title: "stack::size(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size 멤버[STL/CLR]"
ms.assetid: 6113e649-a4f9-4021-8131-34cee4bc8ca0
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# stack::size(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소의 수를 셉니다.  
  
## 구문  
  
```  
size_type size();  
```  
  
## 설명  
 The member function returns the length of the controlled sequence.  You use it to determine the number of elements currently in the controlled sequence.  If all you care about is whether the sequence has nonzero size, see [stack::empty](../dotnet/stack-empty-stl-clr.md)`()`.  
  
## 예제  
  
```  
// cliext_stack_size.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3 starting with 3**  
**size\(\) \= 2 after popping**  
**size\(\) \= 4 after adding 2**   
## 요구 사항  
 **Header:** \<cliext\/stack\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [stack](../dotnet/stack-stl-clr.md)   
 [stack::empty](../dotnet/stack-empty-stl-clr.md)