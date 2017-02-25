---
title: "deque::resize(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize 멤버[STL/CLR]"
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::resize(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소 수를 변경합니다.  
  
## 구문  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### 매개 변수  
 new\_size  
 New size of the controlled sequence.  
  
 val  
 Value of the padding element.  
  
## 설명  
 The member functions both ensure that [deque::size](../dotnet/deque-size-stl-clr.md)`()` henceforth returns `new_size`.  If it must make the controlled sequence longer, the first member function appends elements with value `value_type()`, while the second member function appends elements with value `val`.  To make the controlled sequence shorter, both member functions effectively erase the last element [deque::size](../dotnet/deque-size-stl-clr.md)`() -` `new_size` times.  You use it to ensure that the controlled sequence has size `new_size`, by either trimming or padding the current controlled sequence.  
  
## 예제  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **x x x x x**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::clear](../dotnet/deque-clear-stl-clr.md)   
 [deque::erase](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert](../dotnet/deque-insert-stl-clr.md)