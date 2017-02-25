---
title: "time_get_byname 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.time_get_byname"
  - "time_get_byname"
  - "xloctime/std::time_get_byname"
  - "std::time_get_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get_byname 클래스"
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# time_get_byname 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The derived template class describes an object that can serve as a locale facet of type `time_get`\<CharType, InputIterator\>.  
  
## 구문  
  
```  
template<class Elem, class InputIterator =   
   istreambuf_iterator<CharType, char_traits<CharType> > >  
   class time_get_byname : public time_get<CharType, InputIterator>  
{  
public:  
    explicit time_get_byname(  
        const char *_Locname,  
         size_t _Refs = 0  
    );  
    explicit time_get_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_get_byname()  
};  
```  
  
#### 매개 변수  
 `_Locname`  
 A named locale.  
  
 `_Refs`  
 An initial reference count.  
  
## 요구 사항  
 Its behavior is determined by the named locale `_Locname`.  Each constructor initializes its base object with [time\_get](../Topic/time_get::time_get.md)\<CharType, InputIterator\>\(`_Refs`\).  
  
## 요구 사항  
 **Header:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)