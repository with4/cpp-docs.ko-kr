---
title: "char_traits&lt;wchar_t&gt; 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.char_traits<wchar_t>"
  - "char_traits<wchar_t>"
  - "string/std::char_traits<wchar_t>"
  - "std::char_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<wchar_t> 클래스"
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# char_traits&lt;wchar_t&gt; 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A class that is a specialization of the template struct **char\_traits\<CharType\>** to an element of type `wchar_t`.  
  
## 구문  
  
```  
template<> struct char_traits<wchar_t>;  
```  
  
## 설명  
 Specialization allows the struct to take advantage of library functions that manipulate objects of this type `wchar_t`.  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [char\_traits 구조체](../standard-library/char-traits-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)