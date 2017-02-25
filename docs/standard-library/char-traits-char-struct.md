---
title: "char_traits&lt;char&gt; 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char>"
  - "std::char_traits<char >"
  - "char_traits<char >"
  - "std.char_traits<char >"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char> 클래스"
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# char_traits&lt;char&gt; 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A struct that is a specialization of the template struct **char\_traits\<CharType\>** to an element of type `char`.  
  
## 구문  
  
```  
template<> struct char_traits<char>;  
```  
  
## 설명  
 Specialization allows the struct to take advantage of library functions that manipulate objects of this type `char`.  
  
## 예제  
 See the typedefs and member functions of the template class [char\_traits Class](../standard-library/char-traits-struct.md)\<**CharType**\> for examples involving elements of type `char`.  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std