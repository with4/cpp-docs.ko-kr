---
title: "range_adapter::range_adapter(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::range_adapter::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter 멤버[STL/CLR]"
ms.assetid: b16af13f-3358-4e82-927d-d0d4986bcb18
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# range_adapter::range_adapter(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructs an adapter object.  
  
## 구문  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### 매개 변수  
 first  
 First iterator to wrap.  
  
 last  
 Second iterator to wrap.  
  
 right  
 Object to copy.  
  
## 설명  
 The constructor:  
  
 `range_adapter();`  
  
 initializes the stored iterator pair with default constructed iterators.  
  
 The constructor:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 initializes the stored iterator pair by copying the pair stored in `right`.  
  
 The constructor:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 initializes the stored iterator pair by copying the pair stored in `*right`.  
  
 The constructor:  
  
 `range_adapter(Iter^ first, last);`  
  
 initializes the stored iterator pair with `first` and `last`.  
  
## 예제  
  
```  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)   
 [range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)