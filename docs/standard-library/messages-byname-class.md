---
title: "messages_byname 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages_byname"
  - "std::messages_byname"
  - "std.messages_byname"
  - "xlocmes/std::messages_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages_byname 클래스"
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# messages_byname 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The derived template class describes an object that can serve as a message facet of a given locale, enabling the retrieval of localized messages.  
  
## 구문  
  
```  
template<class CharType>  
    class messages_byname : public messages<CharType> {  
public:  
    explicit messages_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit messages_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~messages_byname();  
};  
```  
  
#### 매개 변수  
 `_Locname`  
 A named locale.  
  
 `_Refs`  
 An initial reference count.  
  
## 설명  
 Its behavior is determined by the named locale `_Locname`.  Each constructor initializes its base object with [messages](../Topic/messages::messages.md)\<CharType\>\(`_Refs`\).  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)