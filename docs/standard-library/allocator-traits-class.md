---
title: "allocator_traits 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::allocator_traits"
  - "memory/std::allocator_traits::propagate_on_container_move_assignment"
  - "memory/std::allocator_traits::const_pointer"
  - "memory/std::allocator_traits::propagate_on_container_swap"
  - "memory/std::allocator_traits::propagate_on_container_copy_assignment"
  - "memory/std::allocator_traits::difference_type"
  - "memory/std::allocator_traits::allocator_type"
  - "memory/std::allocator_traits::value_type"
  - "memory/std::allocator_traits::pointer"
  - "memory/std::allocator_traits::size_type"
  - "memory/std::allocator_traits::const_void_pointer"
  - "memory/std::allocator_traits::void_pointer"
dev_langs: 
  - "C++"
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# allocator_traits 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that supplements an *allocator type*.  An allocator type is any type that describes an allocator object that is used for managing allocated storage.  Specifically, for any allocator type `Alloc`, you can use `allocator_traits<Alloc>` to determine all the information that is needed by an allocator\-enabled container.  For more information, see the default [allocator 클래스](../standard-library/allocator-class.md).  
  
## 구문  
  
```cpp  
template<class Alloc>  
    class allocator_traits;  
```  
  
### 형식 정의  
  
|Name|설명|  
|----------|--------|  
|`allocator_traits::allocator_type`|This type is a synonym for the template parameter `Alloc`.|  
|`allocator_traits::const_pointer`|This type is `Alloc::const_pointer`, if that type is well\-formed; otherwise, this type is `pointer_traits<pointer>::rebind<const value_type>`.|  
|`allocator_traits::const_void_pointer`|This type is `Alloc::const_void_pointer`, if that type is well\-formed; otherwise, this type is `pointer_traits<pointer>::rebind<const void>`.|  
|`allocator_traits::difference_type`|This type is `Alloc::difference_type`, if that type is well\-formed; otherwise, this type is `pointer_traits<pointer>::difference_type`.|  
|`allocator_traits::pointer`|This type is `Alloc::pointer`, if that type is well\-formed; otherwise, this type is `value_type *`.|  
|`allocator_traits::propagate_on_container_copy_assignment`|This type is `Alloc::propagate_on_container_copy_assignment`, if that type is well\-formed; otherwise, this type is `false_type`.|  
|`allocator_traits::propagate_on_container_move_assignment`|This type is `Alloc::propagate_on_container_move_assignment`, if that type is well\-formed; otherwise, this type is `false_type`.  If the type holds true, an allocator\-enabled container copies its stored allocator on a move assignment.|  
|`allocator_traits::propagate_on_container_swap`|This type is `Alloc::propagate_on_container_swap`, if that type is well\-formed; otherwise, this type is `false_type`.  If the type holds true, an allocator\-enabled container swaps its stored allocator on a swap.|  
|`allocator_traits::size_type`|This type is `Alloc::size_type`, if that type is well\-formed; otherwise, this type is `make_unsigned<difference_type>::type`.|  
|`allocator_traits::value_type`|This type is a synonym for `Alloc::value_type`.|  
|`allocator_traits::void_pointer`|This type is `Alloc::void_pointer`, if that type is well\-formed; otherwise, this type is `pointer_traits<pointer>::rebind<void>`.|  
  
### 정적 메서드  
 The following static methods call the corresponding method on a given allocator parameter.  
  
|Name|설명|  
|----------|--------|  
|[allocator\_traits::allocate 메서드](../Topic/allocator_traits::allocate%20Method.md)|Static method that allocates memory by using the given allocator parameter.|  
|[allocator\_traits::construct 메서드](../Topic/allocator_traits::construct%20Method.md)|Static method that uses a specified allocator to construct an object.|  
|[allocator\_traits::deallocate 메서드](../Topic/allocator_traits::deallocate%20Method.md)|Static method that uses a specified allocator to deallocate a specified number of objects.|  
|[allocator\_traits::destroy 메서드](../Topic/allocator_traits::destroy%20Method.md)|Static method that uses a specified allocator to call the destructor on an object without deallocating its memory.|  
|[allocator\_traits::max\_size 메서드](../Topic/allocator_traits::max_size%20Method.md)|Static method that uses a specified allocator to determine the maximum number of objects that can be allocated.|  
|[allocator\_traits::select\_on\_container\_copy\_construction 메서드](../Topic/allocator_traits::select_on_container_copy_construction%20Method.md)|Static method that calls `select_on_container_copy_construction` on the specified allocator.|  
  
## 요구 사항  
 **헤더** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<memory\>](../standard-library/memory.md)   
 [pointer\_traits 구조체](../standard-library/pointer-traits-struct.md)   
 [scoped\_allocator\_adaptor 클래스](../standard-library/scoped-allocator-adaptor-class.md)