---
title: "hash_multimap::hash_delegate(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap::hash_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_delegate 멤버[STL/CLR]"
ms.assetid: 2a459f6d-9bb1-4b03-a013-0998ba842c25
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::hash_delegate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 키와 일치하는 요소를 찾습니다.  
  
## 구문  
  
```  
hasher^ hash_delegate();  
```  
  
## 설명  
 멤버 함수는 키 값을 정수로 변환 하는데 사용 되는 대리자를 반환합니다.  해시 키를 사용합니다.  
  
## 예제  
  
```  
// cliext_hash_multimap_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
  **hash\(L'a'\) \= 1616896120**  
**hash\(L'b'\) \= 570892832**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::hasher](../dotnet/hash-multimap-hasher-stl-clr.md)