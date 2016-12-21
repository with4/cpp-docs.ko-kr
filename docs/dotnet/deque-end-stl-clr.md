---
title: "deque::end(STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end 멤버[STL/CLR]"
ms.assetid: 3de3e816-3334-4b39-97ad-6f8771e9b4e9
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::end(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스의 끝을 지정합니다.  
  
## 구문  
  
```  
iterator end();  
```  
  
## 설명  
 The member function returns a random\-access iterator that points just beyond the end of the controlled sequence.  이를 통해 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.  
  
## 예제  
  
```  
// cliext_deque_end.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::deque<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-end\(\) \= b**  
**\*\-\-end\(\) \= c**  
 **a x y**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::back](../dotnet/deque-back-stl-clr.md)   
 [deque::back\_item](../dotnet/deque-back-item-stl-clr.md)   
 [deque::begin](../dotnet/deque-begin-stl-clr.md)