---
title: "char_traits&lt;char32_t&gt; 구조체 | Microsoft Docs"
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
  - "string/std::char_traits<char_32t>"
  - "char_traits<char32_t>"
  - "std.char_traits<char_32t>"
  - "std::char_traits<char_32t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char32_t> 클래스"
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits&lt;char32_t&gt; 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A struct that is a specialization of the template struct **char\_traits\<CharType\>** to an element of type `char32_t`.  
  
## 구문  
  
```  
template<> struct char_traits<char32_t>;  
```  
  
## 설명  
 Specialization allows the struct to take advantage of library functions that manipulate objects of this type `char32_t`.  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<string\>](../standard-library/string.md)   
 [char\_traits 구조체](../standard-library/char-traits-struct.md)