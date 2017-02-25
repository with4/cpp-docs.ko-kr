---
title: "multimap::find(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find 멤버[STL/CLR]"
ms.assetid: 94b42497-3be4-448c-8de9-0a072ae14fbf
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::find(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 키와 일치하는 요소를 찾습니다.  
  
## 구문  
  
```  
iterator find(key_type key);  
```  
  
#### 매개 변수  
 key  
 Key value to search for.  
  
## 설명  
 If at least one element in the controlled sequence has equivalent ordering with `key`, the member function returns an iterator designating one of those elements; otherwise it returns [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`.  You use it to locate an element currently in the controlled sequence that matches a specified key.  
  
## 예제  
  
```  
// cliext_multimap_find.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymultimap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**find A \= False**  
**find b \= \[b 2\]**  
**find C \= False**   
## 설명  
 Note that `find` does not guarantee which of several element it finds.  
  
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)   
 [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)   
 [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)