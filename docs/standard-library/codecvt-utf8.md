---
title: "codecvt_utf8 | Microsoft Docs"
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
  - "std.codecvt_utf8"
  - "std::codecvt_utf8"
  - "codecvt_utf8"
  - "codecvt/std::codecvt_utf8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8 클래스"
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a [locale](../standard-library/locale-class.md) facet that converts between wide characters encoded as UCS\-2 or UCS\-4, and a byte stream encoded as UTF\-8.  
  
## 구문  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Elem`|The wide\-character element type.|  
|`Maxcode`|The maximum number of characters for the locale facet.|  
|`Mode`|Configuration information for the locale facet.|  
  
## 설명  
 The byte stream can be written to either a binary file or a text file.  
  
## 요구 사항  
 **Header:** \<codecvt\>  
  
 **네임스페이스:** std