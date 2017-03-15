---
title: "map::key_type(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::key_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_type 멤버[STL/CLR]"
ms.assetid: 5bcf92e4-d9ff-48a2-86da-e24842ccf80c
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# map::key_type(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정렬 키의 형식입니다.  
  
## 구문  
  
```  
typedef Key key_type;  
```  
  
## 설명  
 The type is a synonym for the template parameter `Key`.  
  
## 예제  
  
```  
// cliext_map_key_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using key_type   
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Mymap::key_type val = it->first;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [map](../dotnet/map-stl-clr.md)   
 [map::key\_compare](../dotnet/map-key-compare-stl-clr.md)   
 [map::mapped\_type](../dotnet/map-mapped-type-stl-clr.md)   
 [map::value\_type](../dotnet/map-value-type-stl-clr.md)