---
title: "aligned_storage 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "aligned_storage"
  - "std::tr1::aligned_storage"
  - "std.tr1.aligned_storage"
  - "std.aligned_storage"
  - "std::aligned_storage"
  - "type_traits/std::aligned_storage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_storage 클래스[TR1]"
  - "aligned_storage"
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# aligned_storage 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

적절하게 정렬된 형식을 만듭니다.  
  
## 구문  
  
```  
template<std::size_t Len, std::size_t Align>  
    struct aligned_storage;  
  
template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>  
    using aligned_storage_t = typename aligned_storage<Len, Align>::type;  
```  
  
#### 매개 변수  
 `Len`  
 개체 크기입니다.  
  
 `Align`  
 개체 정렬입니다.  
  
## 설명  
 템플릿 멤버 typedef `type` 맞춤을 사용 하 여 POD 형식의 동의어 `Align` 및 크기 `Len`합니다.`Align` 와 동일 해야 `alignment_of<T>::value` 일부 형식에 대 한 `T`, 또는 기본 맞춤을 합니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
typedef std::aligned_storage<sizeof (int),   
    std::alignment_of<double>::value>::type New_type;   
int main()   
    {   
    std::cout << "alignment_of<int> == "   
        << std::alignment_of<int>::value << std::endl;   
    std::cout << "aligned to double == "   
        << std::alignment_of<New_type>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
alignment_of < int > double로 정렬 하는 4 = = 8 = =  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of 클래스](../standard-library/alignment-of-class.md)