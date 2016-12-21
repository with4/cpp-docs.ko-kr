---
title: "moneypunct_byname 클래스 | Microsoft Docs"
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
  - "std.moneypunct_byname"
  - "std::moneypunct_byname"
  - "xlocmon/std::moneypunct_byname"
  - "moneypunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct_byname 클래스"
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# moneypunct_byname 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A derived template class that describes an object that can serve as a `moneypunct` facet of a given locale, enabling the formatting monetary input field or monetary output fields.  
  
## 구문  
  
```  
template<class CharType, bool Intl = false>  
class moneypunct_byname : public moneypunct<CharType, Intl>  
{  
public:  
    explicit moneypunct_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit moneypunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~moneypunct_byname();  
};  
```  
  
## 설명  
 Its behavior is determined by the named locale `_Locname`.  Each constructor initializes its base object with [moneypunct](../Topic/moneypunct::moneypunct.md)\<CharType, Intl\>\(`_Refs`\).  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)