---
title: "const_mem_fun_t 클래스 | Microsoft Docs"
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
  - "const_mem_fun_t"
  - "std.const_mem_fun_t"
  - "xfunctional/std::const_mem_fun_t"
  - "std::const_mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_t 클래스"
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_mem_fun_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단항 함수 개체로 호출되어 참조 인수를 사용하여 초기화될 때 인수를 취하지 않는 상수 멤버 함수를 사용할 수 있는 어댑터 클래스  
  
## 구문  
  
```  
template<class Result, class Type>  
   class const_mem_fun_t : public unary_function <Type *, Result>   
   {  
   explicit const_mem_fun_t( Result ( Type::* _Pm )( ) const );  
   Result operator()(  
      const Type* _Pleft  
   ) const;  
   };  
```  
  
#### 매개 변수  
 `_Pm`  
 A pointer to the member function of class **Type** to be converted to a function object.  
  
 `_Pleft`  
 The object that the `_Pm` member function is called on.  
  
## 반환 값  
 An adaptable unary function.  
  
## 설명  
 The template class stores a copy of `_Pm`, which must be a pointer to a member function of class **Type**, in a private member object.  It defines its member function `operator()` as returning \(`_Pleft`\-\>\* `_Pm`\)\(\) **const**.  
  
## 예제  
 The constructor of `const_mem_fun_t` is not usually used directly; the helper function `mem_fun` is used to adapt member functions.  See [mem\_fun](../Topic/mem_fun%20Function.md) for an example of how to use member function adaptors.  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)