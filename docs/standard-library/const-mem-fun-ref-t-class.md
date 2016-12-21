---
title: "const_mem_fun_ref_t 클래스 | Microsoft Docs"
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
  - "std::const_mem_fun_ref_t"
  - "const_mem_fun_ref_t"
  - "std.const_mem_fun_ref_t"
  - "xfunctional/std::const_mem_fun_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_ref_t 클래스"
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_mem_fun_ref_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An adapter class that allows a **const** member function that takes no arguments to be called as a unary function object when initialized with a reference argument.  
  
## 구문  
  
```  
template<class Result, class Type>  
   class const_mem_fun_ref_t  
      : public unary_function<Type, Result>   
   {  
   explicit const_mem_fun_t(Result ( Type::* _Pm)( ) const );  
   Result operator()(  
      const Type& _Left  
   ) const;  
   };  
```  
  
#### 매개 변수  
 `_Pm`  
 A pointer to the member function of class **Type** to be converted to a function object.  
  
 `_Left`  
 The object that the `_Pm` member function is called on.  
  
## 반환 값  
 An adaptable unary function.  
  
## 설명  
 The template class stores a copy of `_Pm`, which must be a pointer to a member function of class **Type**, in a private member object.  It defines its member function `operator()` as returning \(**\_Left**.\* `_Pm`\)\(\) **const**.  
  
## 예제  
 The constructor of `const_mem_fun_ref_t` is not usually used directly; the helper function `mem_fun_ref` is used to adapt member functions.  See [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) for an example of how to use member function adaptors.  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)