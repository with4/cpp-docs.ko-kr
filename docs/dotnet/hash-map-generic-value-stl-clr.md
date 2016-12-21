---
title: "hash_map::generic_value(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value 멤버[STL/CLR]"
ms.assetid: e370feb3-3d2d-493e-b29d-4e97756c33b0
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::generic_value(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The type of an element for use with the generic interface for the container.  
  
## 구문  
  
```  
typedef GValue generic_value;  
```  
  
## 설명  
 The type describes an object of type `GValue` that describes the stored element value for use with the generic interface for this template container class.  
  
## 예제  
  
```  
// cliext_hash_map_generic_value.cpp   
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
  
// construct a generic container   
    Myhash_map::generic_container^ gc1 = %c1;   
    for each (Myhash_map::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_map::generic_iterator gcit = gc1->begin();   
    Myhash_map::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\]**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)   
 [hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)   
 [hash\_map::generic\_reverse\_iterator](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)