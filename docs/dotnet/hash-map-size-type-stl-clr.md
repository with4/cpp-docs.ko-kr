---
title: "hash_map::size_type(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type 멤버[STL/CLR]"
ms.assetid: 062901e1-b52b-41e4-81be-b6646879e22a
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::size_type(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
## 구문  
  
```  
typedef int size_type;  
```  
  
## 설명  
 형식은 음이 아닌 요소 수를 설명합니다.  
  
## 예제  
  
```  
// cliext_hash_map_size_type.cpp   
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
  
// compute positive difference   
    Myhash_map::size_type diff = 0;   
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**end\(\)\-begin\(\) \= 3**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::empty](../dotnet/hash-map-empty-stl-clr.md)