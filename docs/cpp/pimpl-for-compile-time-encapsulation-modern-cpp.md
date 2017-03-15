---
title: "컴파일 타임 캡슐화에 대한 Pimpl(최신 C++) | Microsoft Docs"
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
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컴파일 타임 캡슐화에 대한 Pimpl(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The *pimpl idiom* is a modern C\+\+ technique to hide implementation, to minimize coupling, and to separate interfaces.  Pimpl is short for "pointer to implementation." You may already be familiar with the concept but know it by other names like Cheshire Cat or Compiler Firewall idiom.  
  
## Why use pimpl?  
 Here's how the pimpl idiom can improve the software development lifecycle:  
  
-   Minimization of compilation dependencies.  
  
-   Separation of interface and implementation.  
  
-   Portability.  
  
## Pimpl header  
  
```cpp  
  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 The pimpl idiom avoids rebuild cascades and brittle object layouts.  It's well suited for \(transitively\) popular types.  
  
## Pimpl implementation  
 Define the `impl` class in the .cpp file.  
  
```cpp  
  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## 모범 사례  
 Consider whether to add support for non\-throwing swap specialization.  
  
## 참고 항목  
 [C\+\+의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)