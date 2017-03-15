---
title: "vector::operator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operatormember [][STL/CLR]"
ms.assetid: 379a7029-460d-4de8-918b-c79e3e13b9d4
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::operator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accesses an element at a specified position.  
  
## 구문  
  
```  
reference operator[](size_type pos);  
```  
  
#### 매개 변수  
 pos  
 액세스할 요소의 위치입니다.  
  
## 설명  
 The member operator returns a referene to the element at position `pos`.  You use it to access an element whose position you know.  
  
## 예제  
  
```  
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a x c**   
## 요구 사항  
 **Header:** \<cliext\/vector\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [vector](../dotnet/vector-stl-clr.md)   
 [vector::at](../dotnet/vector-at-stl-clr.md)