---
title: "operator&gt;= (list)(STL/CLR) | Microsoft Docs"
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
  - "cliext::list::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator>= 멤버[STL/CLR]"
ms.assetid: c6142241-8e85-4759-98fd-4f2b7d37b255
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt;= (list)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

List greater than or equal comparison.  
  
## 구문  
  
```  
template<typename Value>  
    bool operator>=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### 매개 변수  
 left  
 Left container to compare.  
  
 right  
 Right container to compare.  
  
## 설명  
 The operator function returns `!(``left` `<` `right``)`.  You use it to test whether `left` is not ordered before `right` when the two lists are compared element by element.  
  
## 예제  
  
```  
// cliext_list_operator_ge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \>\= \[a b c\] is True**  
**\[a b c\] \>\= \[a b d\] is False**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)   
 [operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)   
 [operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)   
 [operator\> \(list\)](../dotnet/operator-greater-than-list-stl-clr.md)   
 [operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)