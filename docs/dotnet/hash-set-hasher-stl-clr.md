---
title: "hash_set::hasher(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::hasher"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hasher 멤버[STL/CLR]"
ms.assetid: 0fafd645-0bdf-4d4c-8630-c536fbc4bd2c
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_set::hasher(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

키를 위한 해싱 대리자입니다.  
  
## 구문  
  
```  
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>  
    hasher;  
```  
  
## 설명  
 형식은 키 값을 정수로 변환하는 대리자를 설명합니다.  
  
## 예제  
  
```  
// cliext_hash_set_hasher.cpp   
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
 [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)