---
title: "hash 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.hash"
  - "xfunctional/std::hash"
  - "hash"
  - "typeindex/std::hash"
  - "std::hash"
  - "std.tr1.hash"
  - "std::tr1::hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash 클래스"
  - "hash 클래스[TR1]"
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 22
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Computes hash code for a value.  
  
## 구문  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## 설명  
 The member function defines a hash function, suitable for mapping values of type `Ty` to a distribution of index values.  The member operator returns a hash code for `_Val`, suitable for use with template classes `unordered_map`, `unordered_multimap`, `unordered_set`, and `unordered_multiset`.  `Ty` may be any scalar type, `string`, `wstring`, `error_code`, `error_condition`, `u16string`, or `u32string`.  
  
## 예제  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **3**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [unordered\_multimap 클래스](../standard-library/unordered-multimap-class.md)   
 [unordered\_multiset 클래스](../standard-library/unordered-multiset-class.md)   
 [\<unordered\_set\>](../standard-library/unordered-set.md)