---
title: "mem_fun1_ref_t 클래스 | Microsoft Docs"
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
  - "xfunctional/std::mem_fun1_ref_t"
  - "std::mem_fun1_ref_t"
  - "mem_fun1_ref_t"
  - "std.mem_fun1_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun1_ref_t 클래스"
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mem_fun1_ref_t 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이항 함수 개체로 호출되어 참조 인수를 사용하여 초기화될 때 하나의 인수를 취하는 **non\_const** 멤버 함수를 사용할 수 있는 어댑터 클래스  
  
## 구문  
  
```  
template<class Result, class Type, class Arg>  
   class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {  
      explicit mem_fun1_ref_t(  
         Result (Type::* _Pm )( Arg )  
      );  
      Result operator()(  
         Type& _Left,   
         Arg _Right  
      ) const;  
   };  
```  
  
#### 매개 변수  
 `_Pm`  
 A pointer to the member function of class **Type** to be converted to a function object.  
  
 `_Left`  
 The object that the `_Pm` member function is called on.  
  
 `_Right`  
 The argument that is being given to `_Pm`.  
  
## 반환 값  
 An adaptable binary function.  
  
## 설명  
 The template class stores a copy of `_Pm`, which must be a pointer to a member function of class **Type**, in a private member object.  It defines its member function `operator()` as returning \(**\_Left**.\* `_Pm`\)\(**\_Right**\).  
  
## 예제  
 The constructor of `mem_fun1_ref_t` is not usually used directly; the helper function `mem_fun_ref` is used to adapt member functions.  See [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) for an example of how to use member function adaptors.  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)