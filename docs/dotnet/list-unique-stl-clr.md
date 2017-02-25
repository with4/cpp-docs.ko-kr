---
title: "list::unique(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique 멤버[STL/CLR]"
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::unique(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 테스트를 통과하는 인접 요소를 제거합니다.  
  
## 구문  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### 매개 변수  
 pred  
 Comparer for element pairs.  
  
## 설명  
 The first member function removes from the controlled sequence \(erases\) every element that compares equal to its preceding element \-\- if element `X` precedes element `Y` and `X == Y`, the member function removes `Y`.  You use it to remove all but one copy of every subsequence of adjacent elements that compare equal.  Note that if the controlled sequence is ordered, such as by calling [list::sort](../dotnet/list-sort-stl-clr.md)`()`, the member function leaves only elements with unique values. \(Hence the name\).  
  
 The second member function behaves the same as the first, except that it removes each element `Y` following an element `X` for which `pred``(X, Y)`.  You use it to remove all but one copy of every subsequence of adjacent elements that satisfy a predicate function or delegate that you specify.  Note that if the controlled sequence is ordered, such as by calling `sort(``pred``)`, the member function leaves only elements that do not have equivalent ordering with any other elements.  
  
## 예제  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a a b c**  
 **a b c**  
 **a a**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::remove](../dotnet/list-remove-stl-clr.md)   
 [list::remove\_if](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)