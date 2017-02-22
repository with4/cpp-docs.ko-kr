---
title: "money_base 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::money_base"
  - "money_base"
  - "std::money_base"
  - "std.money_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_base 클래스"
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# money_base 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The class describes an enumeration and a structure common to all specializations of template class [moneypunct](../standard-library/moneypunct-class.md).  
  
## 구문  
  
```  
struct money_base : public locale::facet  
{  
    enum  
    {  
        symbol = '$',  
        sign = '+',  
        space = ' ',  
        value = 'v',  
        none = 'x'  
    };  
    typedef int part;  
    struct pattern  
    {  
        char field[_PATTERN_FIELD_SIZE];  
    };  
    money_base(  
        size_t _Refs = 0  
    );  
    ~money_base();  
};  
```  
  
## 설명  
 The enumeration **part** describes the possible values in elements of the array field in the structure pattern.  The values of **part** are:  
  
-   **none** to match zero or more spaces or generate nothing.  
  
-   **sign** to match or generate a positive or negative sign.  
  
-   **space** to match zero or more spaces or generate a space.  
  
-   **symbol** to match or generate a currency symbol.  
  
-   **value** to match or generate a monetary value.  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)