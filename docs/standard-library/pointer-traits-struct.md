---
title: "pointer_traits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::pointer_traits::element_type"
  - "memory/std::pointer_traits::pointer"
  - "memory/std::pointer_traits"
  - "memory/std::pointer_traits::difference_type"
  - "memory/std::pointer_traits::rebind"
  - "xmemory0/std::pointer_traits::element_type"
  - "xmemory0/std::pointer_traits::pointer"
  - "xmemory0/std::pointer_traits"
  - "xmemory0/std::pointer_traits::difference_type"
  - "xmemory0/std::pointer_traits::rebind"
dev_langs: 
  - "C++"
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# pointer_traits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

포인터 형식 `Ptr`를 사용하여 할당자를 설명하기 위해 템플릿 클래스 `allocator_traits`의 개체에 필요한 정보를 제공합니다.  
  
## 구문  
  
```cpp  
template<class Ptr>  
    struct pointer_traits;  
```  
  
## 설명  
 Ptr can be a raw pointer of type `Ty *` or a class with the following properties.  
  
```  
template<class Ty, class... Rest>  
    struct Ptr  
    { // describes a pointer type usable by allocators  
    typedef Ptr pointer;  
    typedef T1 element_type; // optional  
    typedef T2 difference_type; // optional  
    template<class Other>  
        using rebind = typename Ptr<Other, Rest...>; // optional  
  
    static pointer pointer_to(element_type& obj); // optional  
    };  
```  
  
> [!WARNING]
>  While the C\+\+ Standard specifies the `rebind` member as an alias template, Visual C\+\+ implements rebind as a `struct`.  
  
### 형식 정의  
  
|Name|설명|  
|----------|--------|  
|`typedef T2 difference_type`|The type `T2` is `Ptr::difference_type` if that type exists, otherwise `ptrdiff_t`.  If `Ptr` is a raw pointer, the type is `ptrdiff_t`.|  
|`typedef T1 element_type`|The type `T1` is `Ptr::element_type` if that type exists, otherwise `Ty`.  If `Ptr` is a raw pointer, the type is `Ty`.|  
|`typedef Ptr pointer`|형식은 `Ptr`입니다.|  
  
### Structs  
  
|Name|설명|  
|----------|--------|  
|`pointer_traits::rebind`|Attempts to convert the underlying pointer type to a specified type.|  
  
### 메서드  
  
|Name|설명|  
|----------|--------|  
|[pointer\_traits::pointer\_to 메서드](../Topic/pointer_traits::pointer_to%20Method.md)|Converts an arbitrary reference to an object of class `Ptr`.|  
  
## 요구 사항  
 **헤더** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<memory\>](../standard-library/memory.md)   
 [allocator\_traits 클래스](../standard-library/allocator-traits-class.md)