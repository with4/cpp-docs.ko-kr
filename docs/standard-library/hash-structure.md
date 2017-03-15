---
title: "hash 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "typeindex/std::hash"
dev_langs: 
  - "C++"
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# hash 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 `val.hash_code()`를 반환할 때의 메서드를 정의합니다. 메서드는 [type\_index](../standard-library/type-index-class.md) 형식의 맵 값을 인덱스 값의 분포로 매핑하는 데 사용하는 해시 함수를 정의합니다.  
  
## 구문  
  
```vb  
template<>  
    struct hash<type_index>  
        : public unary_function<type_index, size_t>  
    { // hashes a typeinfo object  
    size_t operator()(type_index val) const;  
    };  
```  
  
## 참고 항목  
 [\<typeindex\>](../standard-library/typeindex.md)