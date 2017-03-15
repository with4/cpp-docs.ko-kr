---
title: "hash_set::rehash(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::rehash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rehash 멤버[STL/CLR]"
ms.assetid: f62bae81-4321-44e1-97d0-77174a13e0de
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_set::rehash(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해시 테이블을 다시 빌드합니다.  
  
## 구문  
  
```  
void rehash();  
```  
  
## 설명  
 The member function rebuilds the hash table, ensuring that [hash\_set::load\_factor](../dotnet/hash-set-load-factor-stl-clr.md)`() <=` [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md).  Otherwise, the hash table increases in size only as needed after an insertion. \(It never automatically decreases in size.\) You use it to adjust the size of the hash table.  
  
## 예제  
  
```  
// cliext_hash_set_rehash.cpp   
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
  
// inspect current parameters   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.25f);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// rehash and redisplay   
    c1.rehash(100);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0.1875**  
**max\_load\_factor\(\) \= 4**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0.1875**  
**max\_load\_factor\(\) \= 0.25**  
**bucket\_count\(\) \= 128**  
**load\_factor\(\) \= 0.0234375**  
**max\_load\_factor\(\) \= 0.25**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::bucket\_count](../dotnet/hash-set-bucket-count-stl-clr.md)   
 [hash\_set::load\_factor](../dotnet/hash-set-load-factor-stl-clr.md)   
 [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md)