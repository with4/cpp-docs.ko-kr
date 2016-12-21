---
title: "hash_set::hash_delegate(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::hash_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_delegate 멤버[STL/CLR]"
ms.assetid: 34e39d2d-f2ef-4755-9201-3cdb4e41ea56
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::hash_delegate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 키와 일치하는 요소를 찾습니다.  
  
## 구문  
  
```  
hasher^ hash_delegate();  
```  
  
## 설명  
 The member function returns the delegate used to convert a key value to an integer.  You use it to hash a key.  
  
## 예제  
  
```  
// cliext_hash_set_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    Myhash_set::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
  **hash\(L'a'\) \= 1616896120**  
**hash\(L'b'\) \= 570892832**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md)