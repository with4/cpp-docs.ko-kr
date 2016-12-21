---
title: "type_index 클래스 | Microsoft Docs"
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
  - "typeindex/std::type_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_index 클래스"
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# type_index 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `type_index` class wraps a pointer to [type\_info 클래스](../cpp/type-info-class.md) to assist in indexing by such objects.  
  
```  
class type_index {  
public:  
    type_index(const type_info& tinfo);  
    const char *name() const;  
    size_t hash_code() const;  
    bool operator==(const type_info& right) const;  
    bool operator!=(const type_info& right) const;  
    bool operator<(const type_info& right) const;  
    bool operator<=(const type_info& right) const;  
    bool operator>(const type_info& right) const;  
    bool operator>=(const type_info& right) const;  
};  
```  
  
 The constructor initializes `ptr` to `&tinfo`.  
  
 `name`가 `ptr->name()`를 반환하는 경우  
  
 `hash_code`은 `ptr->hash_code().`를 반환합니다.  
  
 `operator==`가 `*ptr == right.ptr`를 반환하는 경우  
  
 `operator!=`가 `!(*this == right)`를 반환하는 경우  
  
 `operator<`가 `*ptr->before(*right.ptr)`를 반환하는 경우  
  
 `operator<=`은 `!(right < *this).`를 반환합니다.  
  
 `operator>`  `` returns `right < *this`.  
  
 `operator>=`가 `!(*this < right)`를 반환하는 경우  
  
## 참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [\<typeindex\>](../standard-library/typeindex.md)