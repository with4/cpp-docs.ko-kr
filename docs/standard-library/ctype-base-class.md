---
title: "ctype_base 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::ctype_base"
  - "std.ctype_base"
  - "ctype_base"
  - "std::ctype_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_base 클래스"
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# ctype_base 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The class serves as a base class for facets of template class [ctype](../standard-library/ctype-class.md).  A base class for the ctype class that is used to define enumeration types used to classify or test characters either individually or within entire ranges.  
  
## 구문  
  
```  
struct ctype_base : public locale::facet  
{  
    enum  
    {  
        alnum, alpha, cntrl, digit, graph,  
        lower, print, punct, space, upper,  
        xdigit  
    };  
    typedef short mask;  
    ctype_base(  
        size_t _Refs = 0  
    );  
    ~ctype_base();  
};  
```  
  
## 설명  
 It defines an enumeration mask.  Each enumeration constant characterizes a different way to classify characters, as defined by the functions with similar names declared in the header \<ctype.h\>.  The constants are:  
  
-   **space** \(function [isspace](../Topic/isspace.md)\)  
  
-   **print** \(function [isprint](../Topic/isprint.md)\)  
  
-   **cntrl** \(function [iscntrl](../Topic/iscntrl.md)\)  
  
-   **upper** \(function [isupper](../Topic/isupper.md)\)  
  
-   **lower** \(function [islower](../Topic/islower.md)\)  
  
-   **digit** \(function [isdigit](../Topic/isdigit.md)\)  
  
-   **punct** \(function [ispunct](../Topic/ispunct.md)\)  
  
-   **xdigit** \(function [isxdigit](../Topic/isxdigit.md)\)  
  
-   **alpha** \(function [isalpha](../Topic/isalpha.md)\)  
  
-   **alnum** \(function [isalnum](../Topic/isalnum.md)\)  
  
-   **graph** \(function [isgraph](../Topic/isgraph.md)\)  
  
 You can characterize a combination of classifications by ORing these constants.  In particular, it is always true that **alnum** \=\= \(**alpha** ``&#124; **digit**\) and **graph** \=\= \(**alnum**``&#124; **punct**\).  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)