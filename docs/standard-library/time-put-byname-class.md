---
title: "time_put_byname 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "time_put_byname"
  - "xloctime/std::time_put_byname"
  - "std.time_put_byname"
  - "std::time_put_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put_byname 클래스"
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# time_put_byname 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식의 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 파생 된 템플릿 클래스 `time_put`\< CharType, OutputIterator \>.  
  
## 구문  
  
```  
template<class CharType,  
 class OutIt = ostreambuf_iterator<CharType, char_traits<CharType> > >  
 class time_put_byname : public time_put<CharType, OutputIterator>  
{  
public:  
    explicit time_put_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit time_put_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_put_byname();  
};  
```  
  
#### 매개 변수  
 `_Locname`  
 로캘 이름입니다.  
  
 `_Refs`  
 초기 참조 횟수입니다.  
  
## 설명  
 해당 동작은 의해 결정 되는 [라는](../Topic/locale::name.md) 로캘 `_Locname`합니다. 각 생성자와 해당 기본 개체를 초기화 합니다. [time\_put](../Topic/time_put::time_put.md)\< CharType, OutputIterator \> \(`_Refs`\).  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)