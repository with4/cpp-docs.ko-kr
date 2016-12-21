---
title: "stack::to_array(STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array 멤버[STL/CLR]"
ms.assetid: e83bd7c4-ffdb-4151-bd2b-c36ca828e12f
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::to_array(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copies the controlled sequence to a new array.  
  
## 구문  
  
```  
cli::array<Value>^ to_array();  
```  
  
## 설명  
 The member function returns an array containing the controlled sequence.  You use it to obtain a copy of the controlled sequence in array form.  
  
## 예제  
  
```  
// cliext_stack_to_array.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c d**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/stack\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [stack](../dotnet/stack-stl-clr.md)