---
title: "multiset::iterator(STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator 멤버[STL/CLR]"
ms.assetid: 0e8fff2a-f90e-4ba6-816a-5a2dc77c51e3
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스에 대한 반복기의 형식입니다.  
  
## 구문  
  
```  
typedef T1 iterator;  
```  
  
## 설명  
 형식은 제어된 시퀀스를 위해 양방향 반복기의 역할을 할 수 있는 지정되지 않은 형식 `T1`의 개체를 설명합니다.  
  
## 예제  
  
```  
// cliext_multiset_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)