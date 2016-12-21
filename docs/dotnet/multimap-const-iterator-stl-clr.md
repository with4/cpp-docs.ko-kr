---
title: "multimap::const_iterator(STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::const_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_iterator 멤버[STL/CLR]"
ms.assetid: 13b166c9-1dcd-4ff9-b1da-3b8ffa463735
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::const_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.  
  
## 구문  
  
```  
typedef T2 const_iterator;  
```  
  
## 설명  
 형식은 제어된 시퀀스를 위해 상수 양방향 반복자의 여 역할을 할 수 있는 지정되지 않은 형식 `T2`의 개체를 설명합니다.  
  
## 예제  
  
```  
// cliext_multimap_const_iterator.cpp   
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
    Mymultimap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" [{0} {1}]", cit->first, cit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)