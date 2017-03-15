---
title: "hash_set::count(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count 멤버[STL/CLR]"
ms.assetid: 99dbaef5-64fd-4bef-bac4-a6072dd231f1
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# hash_set::count(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Finds the number of elements matching a specified key.  
  
## 구문  
  
```  
size_type count(key_type key);  
```  
  
#### 매개 변수  
 key  
 Key value to search for.  
  
## 설명  
 The member function returns the number of elements in the controlled sequence that have equivalent ordering with `key`.  이를 통해 현재 제어되는 시퀀스에 있는 요소 중 지정된 키와 일치하는 요소의 수를 확인할 수 있습니다.  
  
## 예제  
  
```  
// cliext_hash_set_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**count\(L'A'\) \= 0**  
**count\(L'b'\) \= 1**  
**count\(L'C'\) \= 0**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)