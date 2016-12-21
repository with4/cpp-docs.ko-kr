---
title: "function 클래스 | Microsoft Docs"
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
  - "functional/std::tr1::function"
  - "std.tr1.function"
  - "std::tr1::function"
  - "function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "function 클래스[TR1]"
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wrapper for a callable object.  
  
## 구문  
  
```cpp  
template<class Fty>  
   class function  // Fty of type Ret(T1, T2, ..., TN)  
   : public unary_function<T1, Ret>       // when Fty is Ret(T1)  
   : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)  
   {  
public:  
   typedef Ret result_type;  
  
   function();  
   function(nullptr_t);  
   function(const function& _Right);  
   template<class Fty2>  
      function(Fty2 fn);  
   template<class Fty2, class Alloc>  
       function (reference_wrapper<Fty2>, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       void assign (Fty2, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       assign (reference_wrapper<Fty2>, const Alloc& _Ax);  
```  
  
```cpp  
function& operator=(nullptr_t);  
function& operator=(const function&);  
template<class Fty2>  
   function& operator=(Fty2);  
template<class Fty2>  
   function& operator=(reference_wrapper<Fty2>);  
void swap(function&);  
  
explicit operator bool() const;  
result_type operator()(T1, T2, ....., TN) const;  
  
const std::type_info& target_type() const;  
template<class Fty2>  
   Fty2 *target();  
template<class Fty2>  
   const Fty2 *target() const;  
```  
  
```cpp  
   template<class Fty2>  
      void operator==(const Fty2&) const = delete;  
   template<class Fty2>  
      void operator!=(const Fty2&) const = delete;  
};  
```  
  
#### 매개 변수  
 `Fty`  
 The function type to wrap.  
  
 `_Ax`  
 The allocator function.  
  
## 설명  
 The template class is a call wrapper whose call signature is `Ret(T1, T2, ..., TN)`.  You use it to enclose a variety of callable objects in a uniform wrapper.  
  
 Some member functions take an operand that names the desired target object.  You can specify such an operand in several ways:  
  
 `fn` \-\- the callable object `fn`; after the call the `function` object holds a copy of `fn`  
  
 `fnref` \-\- the callable object named by `fnref.get()`; after the call the `function` object holds a reference to `fnref.get()`  
  
 `right` \-\- the callable object, if any, held by the `function` object `right`  
  
 `npc` \-\- a null pointer; after the call the `function` object is empty  
  
 In all cases, `INVOKE(f, t1, t2, ..., tN)`, where `f` is the callable object and `t1, t2, ..., tN` are lvalues of types `T1, T2, ..., TN` respectively, must be well\-formed and, if `Ret` is not void, convertible to `Ret`.  
  
 An empty `function` object does not hold a callable object or a reference to a callable object.  
  
### 생성자  
  
|||  
|-|-|  
|[function::function](../Topic/function::function.md)|Constructs a wrapper that either is empty or stores a callable object of arbitrary type with a fixed signature.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[function::result\_type](../Topic/function::result_type.md)|The return type of the stored callable object.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[function::assign](../Topic/function::assign.md)|Assigns a callable object to this function object.|  
|[function::swap](../Topic/function::swap.md)|Swap two callable objects.|  
|[function::target](../Topic/function::target.md)|Tests if stored callable object is callable as specified.|  
|[function::target\_type](../Topic/function::target_type.md)|Gets type information on the callable object.|  
  
### 연산자  
  
|||  
|-|-|  
|[function::operator unspecified](../Topic/function::operator%20unspecified.md)|Tests if stored callable object exists.|  
|[function::operator\(\)](../Topic/function::operator\(\).md)|Calls a callable object.|  
|[function::operator\=](../Topic/function::operator=.md)|Replaces the stored callable object.|  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [mem\_fn 함수](../Topic/mem_fn%20Function.md)   
 [reference\_wrapper 클래스](../standard-library/reference-wrapper-class.md)