---
title: "regex_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::regex_iterator"
  - "std.tr1.regex_iterator"
  - "regex_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_iterator 클래스[TR1]"
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# regex_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일치 항목에 대한 반복기 클래스입니다.  
  
## 구문  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef match_results<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const match_results<BidIt>* pointer;  
    typedef const match_results<BidIt>& reference;  
  
    regex_iterator();  
    regex_iterator(BidIt first, BidIt last,  
        const regex_type& re,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_iterator& right);  
    bool operator!=(const regex_iterator& right);  
    const match_results<BidIt>& operator*();  
    const match_results<BidIt> *operator->();  
    regex_iterator& operator++();  
    regex_iterator& operator++(int);  
  
    BidIt begin;                            // exposition only  
    BidIt end;                              // exposition only  
    regex_type *pregex;                     // exposition only  
    regex_constants::match_flag_type flags; // exposition only  
    match_results<BidIt> match;             // exposition only  
    };  
```  
  
#### 매개 변수  
 `BidIt`  
 부분 일치에 대한 반복기 형식입니다.  
  
 `Elem`  
 일치 항목을 찾을 요소의 형식입니다.  
  
 `RXtraits`  
 요소에 대한 특성 클래스입니다.  
  
## 설명  
 템플릿 클래스는 일정한 정방향 반복기 개체를 설명합니다. 반복기 범위 `[begin, end)`에 정의된 문자 시퀀스에 정규식 개체 `*pregex`를 반복적으로 적용하여 `match_results<BidIt>` 형식의 개체를 추출합니다.  
  
## 예제  
 정규식에 대한 예제는 다음 항목을 참조하세요.  
  
-   [regex\_match 함수](../Topic/regex_match%20Function.md)  
  
-   [regex\_replace 함수](../Topic/regex_replace%20Function.md)  
  
-   [regex\_search 함수](../Topic/regex_search%20Function.md)  
  
-   [swap 함수](../Topic/swap%20Function%20%3Cregex%3E.md)  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_iterator](../standard-library/regex-iterator-class.md)