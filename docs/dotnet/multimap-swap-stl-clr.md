---
title: "multimap::swap(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap 멤버[STL/CLR]"
ms.assetid: 198018d2-7814-4237-8ec3-5f3ea950e8af
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::swap(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 컨테이너의 내용을 바꿉니다.  
  
## 구문  
  
```  
void swap(multimap<Key, Mapped>% right);  
```  
  
#### 매개 변수  
 right  
 내용을 바꿀 컨테이너입니다.  
  
## 설명  
 멤버 함수는 `this` 와 `right`사이에서 제어되는 시퀀스를 맞바꿉니다.  일정한 시간에는 그렇고 예외가 발생하지않습니다.  두 컨테이너들의 내용을 바꾸는 빠른 방법으로 그것을 사용합니다.  
  
## 예제  
  
```  
// cliext_multimap_swap.cpp   
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
  
// construct another container with repetition of values   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'd', 4));   
    c2.insert(Mymultimap::make_value(L'e', 5));   
    c2.insert(Mymultimap::make_value(L'f', 6));   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[d, 4\] \[e, 5\] \[f, 6\]**  
 **\[d, 4\] \[e, 5\] \[f, 6\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)