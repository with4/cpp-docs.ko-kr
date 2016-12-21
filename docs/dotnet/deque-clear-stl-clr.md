---
title: "deque::clear(STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::clear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clear 멤버[STL/CLR]"
ms.assetid: 1d9a3d11-b3fa-43a7-a508-7a05cbcd91bf
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::clear(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 요소를 제거합니다.  
  
## 구문  
  
```  
void clear();  
```  
  
## 설명  
 멤버함수는 효율적으로 [deque::erase](../dotnet/deque-erase-stl-clr.md)`(` [deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` [deque::end](../dotnet/deque-end-stl-clr.md)`())`을 호출합니다.  제어되는 시퀀스 비어 있는지 확인하기 위해 사용합니다.  
  
## 예제  
  
```  
// cliext_deque_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 0**  
 **a b**  
**size\(\) \= 0**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::erase](../dotnet/deque-erase-stl-clr.md)