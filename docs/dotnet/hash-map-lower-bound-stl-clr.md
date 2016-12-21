---
title: "hash_map::lower_bound(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::lower_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lower_bound 멤버[STL/CLR]"
ms.assetid: 7c88987a-9c77-4874-8052-192a148abbf1
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::lower_bound(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Finds beginning of range that matches a specified key.  
  
## 구문  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### 매개 변수  
 key  
 Key value to search for.  
  
## 설명  
 The member function determines the first element `X` in the controlled sequence that hashes to the same bucket as `key` and has equivalent ordering to `key`.  If no such element exists, it returns [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`; otherwise it returns an iterator that designates `X`.  You use it to locate the beginning of a sequence of elements currently in the controlled sequence that match a specified key.  
  
## 예제  
  
```  
// cliext_hash_map_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Myhash_map::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**lower\_bound\(L'x'\)\=\=end\(\) \= True**  
**\*lower\_bound\(L'a'\) \= \[a 1\]**  
**\*lower\_bound\(L'b'\) \= \[b 2\]**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::count](../dotnet/hash-map-count-stl-clr.md)   
 [hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash\_map::find](../dotnet/hash-map-find-stl-clr.md)   
 [hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)