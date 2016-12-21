---
title: "hash_set::rend(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend 멤버[STL/CLR]"
ms.assetid: 12764bf1-ff3e-48db-a6ef-fe120187bc4e
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::rend(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

역방향 제어되는 시퀀스의 끝을 지정합니다.  
  
## 구문  
  
```  
reverse_iterator rend();  
```  
  
## 설명  
 멤버 함수는 제어된 시퀀스의 시작 바로 뒤를 가리키는 역방향 반복기를 반환합니다.  따라서 역방향 시퀀스의 `end`를 지정합니다.  이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.  
  
## 예제  
  
```  
// cliext_hash_set_rend.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myhash_set::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-rend\(\) \= b**  
**\*\-\-rend\(\) \= a**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)   
 [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)   
 [hash\_set::rbegin](../dotnet/hash-set-rbegin-stl-clr.md)