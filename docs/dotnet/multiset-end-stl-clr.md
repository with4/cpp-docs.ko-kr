---
title: "multiset::end(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end 멤버[STL/CLR]"
ms.assetid: 225f8b74-f9b9-47ea-9603-43ac7c9a9734
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# multiset::end(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스의 끝을 지정합니다.  
  
## 구문  
  
```  
iterator end();  
```  
  
## 설명  
 The member function returns a bidirectional iterator that points just beyond the end of the controlled sequence.  You use it to obtain an iterator that designates the end of the controlled sequence; its status doesn not change if the length of the controlled sequence changes.  
  
## 예제  
  
```  
// cliext_multiset_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-end\(\) \= b**  
**\*\-\-end\(\) \= c**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::begin](../dotnet/multiset-begin-stl-clr.md)