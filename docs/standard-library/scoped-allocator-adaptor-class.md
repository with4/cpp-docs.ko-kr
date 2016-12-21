---
title: "scoped_allocator_adaptor 클래스 | Microsoft Docs"
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
  - "std.scoped_allocator_adaptor"
  - "scoped_allocator_adaptor"
  - "scoped_allocator/std::scoped_allocator_adaptor"
  - "std::scoped_allocator_adaptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scoped_allocator_adaptor 클래스"
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# scoped_allocator_adaptor 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a nest of allocators.  
  
## 구문  
  
```cpp  
template<class Outer, class... Inner>  
    class scoped_allocator_adaptor;  
```  
  
## 설명  
 The template class encapsulates a nest of one or more allocators.  Each such class has an outermost allocator of type `outer_allocator_type`, a synonym for `Outer`, which is a public base of the `scoped_allocator_adaptor` object.  `Outer` is used to allocate memory to be used by a container.  You can obtain a reference to this allocator base object by calling `outer_allocator`.  
  
 The remainder of the nest has type `inner_allocator_type`.  An inner allocator is used to allocate memory for elements within a container.  You can obtain a reference to the stored object of this type by calling `inner_allocator`.  If `Inner...` is not empty, `inner_allocator_type` has type `scoped_allocator_adaptor<Inner...>`, and `inner_allocator` designates a member object.  Otherwise, `inner_allocator_type` has type `scoped_allocator_adaptor<Outer>`, and `inner_allocator` designates the entire object.  
  
 The nest behaves as if it has arbitrary depth, replicating its innermost encapsulated allocator as needed.  
  
 Several concepts that are not a part of the visible interface aid in describing the behavior of this template class.  An *outermost allocator* mediates all calls to the construct and destroy methods.  It is effectively defined by the recursive function `OUTERMOST(X)`, where `OUTERMOST(X)` is one of the following.  
  
-   If `X.outer_allocator()` is well formed, then `OUTERMOST(X)` is `OUTERMOST(X.outer_allocator())`.  
  
-   그렇지 않으면 `OUTERMOST(X)`는 `X`입니다.  
  
 Three types are defined for the sake of exposition:  
  
|형식|설명|  
|--------|--------|  
|`Outermost`|`OUTERMOST(*this)`의 형식입니다.|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### 생성자  
  
|Name|설명|  
|----------|--------|  
|[scoped\_allocator\_adaptor::scoped\_allocator\_adaptor 생성자](../Topic/scoped_allocator_adaptor::scoped_allocator_adaptor%20Constructor.md)|`scoped_allocator_adaptor` 개체를 생성합니다.|  
  
### 형식 정의  
  
|Name|설명|  
|----------|--------|  
|`const_pointer`|This type is a synonym for the `const_pointer` that is associated with the allocator `Outer`.|  
|`const_void_pointer`|This type is a synonym for the `const_void_pointer` that is associated with the allocator `Outer`.|  
|`difference_type`|This type is a synonym for the `difference_type` that is associated with the allocator `Outer`.|  
|`inner_allocator_type`|This type is a synonym for the type of the nested adaptor `scoped_allocator_adaptor<Inner...>`.|  
|`outer_allocator_type`|This type is a synonym for the type of the base allocator `Outer`.|  
|`pointer`|This type is a synonym for the `pointer` associated with the allocator `Outer`.|  
|`propagate_on_container_copy_assignment`|The type holds true only if `Outer_traits::propagate_on_container_copy_assignment` holds true or `inner_allocator_type::propagate_on_container_copy_assignment` holds true.|  
|`propagate_on_container_move_assignment`|The type holds true only if `Outer_traits::propagate_on_container_move_assignment` holds true or `inner_allocator_type::propagate_on_container_move_assignment` holds true.|  
|`propagate_on_container_swap`|The type holds true only if `Outer_traits::propagate_on_container_swap` holds true or `inner_allocator_type::propagate_on_container_swap` holds true.|  
|`size_type`|This type is a synonym for the `size_type` associated with the allocator `Outer`.|  
|`value_type`|This type is a synonym for the `value_type` associated with the allocator `Outer`.|  
|`void_pointer`|This type is a synonym for the `void_pointer` associated with the allocator `Outer`.|  
  
### Structs  
  
|Name|설명|  
|----------|--------|  
|[scoped\_allocator\_adaptor::rebind 구조체](../Topic/scoped_allocator_adaptor::rebind%20Struct.md)|Defines the type `Outer::rebind<Other>::other` as a synonym for `scoped_allocator_adaptor<Other, Inner...>`.|  
  
### 메서드  
  
|Name|설명|  
|----------|--------|  
|[scoped\_allocator\_adaptor::allocate 메서드](../Topic/scoped_allocator_adaptor::allocate%20Method.md)|Allocates memory by using the `Outer` allocator.|  
|[scoped\_allocator\_adaptor::construct 메서드](../Topic/scoped_allocator_adaptor::construct%20Method.md)|Constructs an object.|  
|[scoped\_allocator\_adaptor::deallocate 메서드](../Topic/scoped_allocator_adaptor::deallocate%20Method.md)|Deallocates objects by using the outer allocator.|  
|[scoped\_allocator\_adaptor::destroy 메서드](../Topic/scoped_allocator_adaptor::destroy%20Method.md)|Destroys a specified object.|  
|[scoped\_allocator\_adaptor::inner\_allocator 메서드](../Topic/scoped_allocator_adaptor::inner_allocator%20Method.md)|Retrieves a reference to the stored object of type `inner_allocator_type`.|  
|[scoped\_allocator\_adaptor::max\_size 메서드](../Topic/scoped_allocator_adaptor::max_size%20Method.md)|Determines the maximum number of objects that can be allocated by the outer allocator.|  
|[scoped\_allocator\_adaptor::outer\_allocator 메서드](../Topic/scoped_allocator_adaptor::outer_allocator%20Method.md)|Retrieves a reference to the stored object of type `outer_allocator_type`.|  
|[scoped\_allocator\_adaptor::select\_on\_container\_copy\_construction 메서드](../Topic/scoped_allocator_adaptor::select_on_container_copy_construction%20Method.md)|Creates a new `scoped_allocator_adaptor` object with each stored allocator object initialized by calling `select_on_container_copy_construction` for each corresponding allocator.|  
  
## 요구 사항  
 **Header:** \<scoped\_allocator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)