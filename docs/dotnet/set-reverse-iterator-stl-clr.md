---
title: "set::reverse_iterator(STL/CLR) | Microsoft Docs"
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
  - "cliext::set::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator 멤버[STL/CLR]"
ms.assetid: 40337a62-991c-424e-9559-a9040c07657a
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::reverse_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The type of a reverse iterator for the controlled sequence.  
  
## 구문  
  
```  
typedef T3 reverse_iterator;  
```  
  
## 설명  
 The type describes an object of unspecified type `T3` that can serve as a reverse iterator for the controlled sequence.  
  
## 예제  
  
```  
// cliext_set_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Myset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [set::const\_iterator](../dotnet/set-const-iterator-stl-clr.md)   
 [set::const\_reverse\_iterator](../dotnet/set-const-reverse-iterator-stl-clr.md)   
 [set::iterator](../dotnet/set-iterator-stl-clr.md)