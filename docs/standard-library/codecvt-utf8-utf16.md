---
title: "codecvt_utf8_utf16 | Microsoft Docs"
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
  - "codecvt_utf8_utf16"
  - "codecvt/std::cvt_utf8_utf16"
  - "std::codecvt_utf8_utf16"
  - "std.codecvt_utf8_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8_utf16 클래스"
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a [locale](../standard-library/locale-class.md) facet that converts between wide characters encoded as UTF\-16 and a byte stream encoded as UTF\-8.  
  
## 구문  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>  
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