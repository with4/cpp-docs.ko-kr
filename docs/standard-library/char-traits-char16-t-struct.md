---
title: "char_traits&lt;char16_t&gt; 구조체 | Microsoft Docs"
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
  - "std::char_traits<char16_t>"
  - "std.char_traits<char16_t>"
  - "char_traits<char16_t>"
  - "string/std::char_traits<char16_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char16_t> 클래스"
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits&lt;char16_t&gt; 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A struct that is a specialization of the template struct **char\_traits\<CharType\>** to an element of type `char16_t`.  
  
## 구문  
  
```  
template<> struct char_traits<char16_t>;  
```  
  
## 설명  
 Specialization allows the struct to take advantage of library functions that manipulate objects of the type `char16_t`.  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<string\>](../standard-library/string.md)   
 [char\_traits 구조체](../standard-library/char-traits-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)