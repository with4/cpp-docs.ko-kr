---
title: "set::rbegin(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin 멤버[STL/CLR]"
ms.assetid: b9da72dc-0b75-489e-b179-74c27a4bcfb7
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# set::rbegin(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

역방향 제어되는 시퀀스의 시작을 지정합니다.  
  
## 구문  
  
```  
reverse_iterator rbegin();  
```  
  
## 설명  
 The member function returns a reverse iterator that designates the last element of the controlled sequence, or just beyond the beginning of an empty sequence.  따라서 역방향 시퀀스의 `beginning`을 지정합니다.  이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.  
  
## 예제  
  
```  
// cliext_set_rbegin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*rbegin\(\) \= c**  
**\*\+\+rbegin\(\) \= b**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [set::begin](../dotnet/set-begin-stl-clr.md)   
 [set::end](../dotnet/set-end-stl-clr.md)   
 [set::rend](../dotnet/set-rend-stl-clr.md)