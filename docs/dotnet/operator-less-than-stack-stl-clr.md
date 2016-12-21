---
title: "operator&lt; (stack)(STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< 멤버[STL/CLR]"
ms.assetid: 77f8dd42-89d1-4ce1-a7ec-04c3a45dd3ee
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (stack)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stack less than comparison.  
  
## 구문  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### 매개 변수  
 left  
 Left container to compare.  
  
 right  
 Right container to compare.  
  
## 설명  
 The operator function returns true if, for the lowest position `i` for which `!(``right``[i] <` `left``[i])` it is also true that `left``[i] <` `right``[i]`.  Otherwise, it returns `left``->`[stack::size](../dotnet/stack-size-stl-clr.md)`() <` `right``->size()` You use it to test whether `left` is ordered before `right` when the two stacks are compared element by element.  
  
## 예제  
  
```  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \< \[a b c\] is False**  
**\[a b c\] \< \[a b d\] is True**   
## 요구 사항  
 **Header:** \<cliext\/stack\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [stack](../dotnet/stack-stl-clr.md)   
 [operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)