---
title: "hash_multimap::reverse_iterator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator 멤버[STL/CLR]"
ms.assetid: 000d3250-befa-4604-b042-11424cb179dc
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_multimap::reverse_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스에 대한 반대 반복기의 형식입니다.  
  
## 구문  
  
```  
typedef T3 reverse_iterator;  
```  
  
## 설명  
 형식은 제어된 시퀀스를 위해 상수 반대 반복기의 역할을 할 수 있는 지정되지 않은 형식 `T3`의 개체를 설명합니다.  
  
## 예제  
  
```  
// cliext_hash_multimap_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_multimap::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" [{0} {1}]", rit->first, rit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[c 3\] \[b 2\] \[a 1\]**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)   
 [hash\_multimap::const\_reverse\_iterator](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)   
 [hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)