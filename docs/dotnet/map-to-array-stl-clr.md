---
title: "map::to_array(STL/CLR) | Microsoft Docs"
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
  - "cliext::map::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array 멤버[STL/CLR]"
ms.assetid: e7089d11-c968-4110-927a-97f9b5b8f992
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::to_array(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copies the controlled sequence to a new array.  
  
## 구문  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## 설명  
 The member function returns an array containing the controlled sequence.  You use it to obtain a copy of the controlled sequence in array form.  
  
## 예제  
  
```  
// cliext_map_to_array.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Mymap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Mymap::make_value(L'd', 4));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Mymap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\] \[d 4\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [map](../dotnet/map-stl-clr.md)