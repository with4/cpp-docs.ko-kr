---
title: "deque::at(STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::at"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "at 멤버[STL/CLR]"
ms.assetid: 9af83d8a-c519-4b2a-a25f-d3dc8bbb87fb
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::at(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accesses an element at a specified position.  
  
## 구문  
  
```  
reference at(size_type pos);  
```  
  
#### 매개 변수  
 pos  
 액세스할 요소의 위치입니다.  
  
## 설명  
 The member function returns a reference to the element of the controlled sequence at position `pos`.  You use it to read or write an element whose position you know.  
  
## 예제  
  
```  
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a x c**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::operator](../dotnet/deque-operator-stl-clr.md)