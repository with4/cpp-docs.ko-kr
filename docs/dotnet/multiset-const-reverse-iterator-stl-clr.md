---
title: "multiset::const_reverse_iterator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator 멤버[STL/CLR]"
ms.assetid: f345ddd5-c871-4a6c-a6a4-b90eb843665c
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multiset::const_reverse_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The type of a constant reverse iterator for the controlled sequence..  
  
## 구문  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## 설명  
 The type describes an object of unspecified type `T4` that can serve as a constant reverse iterator for the controlled sequence.  
  
## 예제  
  
```  
// cliext_multiset_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)