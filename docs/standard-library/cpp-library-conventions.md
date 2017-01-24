---
title: "C++ 라이브러리 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스[C++]"
  - "코딩 규칙, 표준 C++ 라이브러리"
  - "규칙[C++], 표준 C++ 라이브러리"
  - "함수 이름[C++]"
  - "함수[C++], 라이브러리 명명 규칙"
  - "명명 규칙[C++], C++ 라이브러리"
  - "명명 규칙[C++], 표준 C++ 라이브러리"
  - "표준 C++ 라이브러리, 규칙"
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ 라이브러리 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The C\+\+ library obeys much the same conventions as the Standard C Library, plus a few more outlined here.  
  
 An implementation has certain latitude in how it declares types and functions in the C\+\+ library:  
  
-   Names of functions in the Standard C library may have either extern \#"C\+\+" or extern "C" linkage.  Include the appropriate Standard C header rather than declare a library entity inline.  
  
-   A member function name in a library class may have additional function signatures over those listed in this document.  You can be sure that a function call described here behaves as expected, but you cannot reliably take the address of a library member function. \(The type may not be what you expect.\)  
  
-   A library class may have undocumented \(nonvirtual\) base classes.  A class documented as derived from another class may, in fact, be derived from that class through other undocumented classes.  
  
-   A type defined as a synonym for some integer type may be the same as one of several different integer types.  
  
-   A bitmask type can be implemented as either an integer type or an enumeration.  In either case, you can perform bitwise operations \(such as `AND` and `OR`\) on values of the same bitmask type.  The elements `A` and `B` of a bitmask type are nonzero values such that `A` & `B` is zero.  
  
-   A library function that has no exception specification can throw an arbitrary exception, unless its definition clearly restricts such a possibility.  
  
 On the other hand, there are some restrictions:  
  
-   The Standard C Library uses no masking macros.  Only specific function signatures are reserved, not the names of the functions themselves.  
  
-   A library function name outside a class will not have additional, undocumented, function signatures.  You can reliably take its address.  
  
-   Base classes and member functions described as virtual are assuredly virtual, while those described as nonvirtual are assuredly nonvirtual.  
  
-   Two types defined by the C\+\+ library are always different unless this document explicitly suggests otherwise.  
  
-   Functions supplied by the library, including the default versions of replaceable functions, can throw *at most* those exceptions listed in any exception specification.  No destructors supplied by the library throw exceptions.  Functions in the Standard C Library may propagate an exception, as when `qsort` calls a comparison function that throws an exception, but they do not otherwise throw exceptions.  
  
## 참고 항목  
 [STL 개요](../standard-library/cpp-standard-library-overview.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)