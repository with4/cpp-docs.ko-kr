---
title: "collection_adapter::size(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size 멤버[STL/CLR]"
ms.assetid: 71866719-9e29-4572-bfb9-60321f2937c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# collection_adapter::size(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소의 수를 셉니다.  
  
## 구문  
  
```  
size_type size();  
```  
  
## 설명  
 The member function returns the length of the controlled sequence.  It is not defined in a specialization for `IEnumerable` or `IEnumerable<Value>`.  
  
## 예제  
  
```  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
**size\(\) \= 6**   
## 요구 사항  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)