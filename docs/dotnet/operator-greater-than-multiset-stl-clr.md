---
title: "operator&gt; (multiset)(STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator> 멤버[STL/CLR]"
ms.assetid: 88b4d56d-c7e9-4ac9-a460-0f26e1e5b837
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt; (multiset)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

List greater than comparison.  
  
## 구문  
  
```  
template<typename Key>  
    bool operator>(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### 매개 변수  
 left  
 Left container to compare.  
  
 right  
 Right container to compare.  
  
## 설명  
 The operator function returns `right` `<` `left`.  You use it to test whether `left` is ordered after `right` when the two multisets are compared element by element.  
  
## 예제  
  
```  
// cliext_multiset_operator_gt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \> \[a b c\] is False**  
**\[a b d\] \> \[a b c\] is True**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)   
 [operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)   
 [operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)   
 [operator\>\= \(multiset\)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)   
 [operator\<\= \(multiset\)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)