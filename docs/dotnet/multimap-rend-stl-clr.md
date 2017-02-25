---
title: "multimap::rend(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend 멤버[STL/CLR]"
ms.assetid: f8d3f683-eeab-4a8b-af3f-fb6653114594
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multimap::rend(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

역방향 제어되는 시퀀스의 끝을 지정합니다.  
  
## 구문  
  
```  
reverse_iterator rend();  
```  
  
## 설명  
 The member function returns a reverse iterator that points just beyond the beginning of the controlled sequence.  따라서 역방향 시퀀스의 `end`를 지정합니다.  이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.  
  
## 예제  
  
```  
// cliext_multimap_rend.cpp   
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
  
// inspect first two items in reversed sequence   
    Mymultimap::reverse_iterator rit = c1.rend();   
    --rit;   
    --rit;   
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*--rend() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**\*\-\- \-\-rend\(\) \= \[b 2\]**  
**\*\-\-rend\(\) \= \[a 1\]**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::begin](../dotnet/multimap-begin-stl-clr.md)   
 [multimap::end](../dotnet/multimap-end-stl-clr.md)   
 [multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)