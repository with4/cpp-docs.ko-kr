---
title: "mem_fun_t 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mem_fun_t"
  - "xfunctional/std::mem_fun_t"
  - "std::mem_fun_t"
  - "std.mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_t 클래스"
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# mem_fun_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단항 함수 개체로 호출되어 포인터 인수를 사용하여 초기화될 때 인수를 취하지 않는 **non\_const** 멤버 함수를 사용할 수 있는 어댑터 클래스  
  
## 구문  
  
```  
template<class Result, class Type>  
   class mem_fun_t : public unary_function<Type *, Result> {  
      explicit mem_fun_t(Result ( Type::*_Pm )( ) );  
      Result operator()( Type* _Pleft ) const;  
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
 The template class stores a copy of `_Pm`, which must be a pointer to a member function of class **Type**, in a private member object.  It defines its member function `operator()` as returning \(`_Pleft`\-\>\* `_Pm`\)\( \).  
  
## 예제  
 The constructor of `mem_fun_t` is not usually used directly; the helper function `mem_fun` is used to adapt member functions.  See [mem\_fun](../Topic/mem_fun%20Function.md) for an example of how to use member function adaptors.  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<functional\>](../standard-library/functional.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)