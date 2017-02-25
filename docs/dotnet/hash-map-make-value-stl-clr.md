---
title: "hash_map::make_value(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value 멤버[STL/CLR]"
ms.assetid: 1fcdcacc-5edf-46b7-9481-9a4aef32b025
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_map::make_value(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructs a value object.  
  
## 구문  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### 매개 변수  
 key  
 Key value to use.  
  
 mapped  
 Mapped value to search for.  
  
## 설명  
 The member function returns a `value_type` object whose key is `key` and whose mapped value is `mapped`.  You use it to compose an object suitable for use with several other member functions.  
  
## 예제  
  
```  
// cliext_hash_map_make_value.cpp   
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
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_type](../dotnet/hash-map-key-type-stl-clr.md)   
 [hash\_map::mapped\_type](../dotnet/hash-map-mapped-type-stl-clr.md)   
 [hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)