---
title: "regex_token_iterator 클래스 | Microsoft Docs"
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
  - "regex_token_iterator"
  - "std.tr1.regex_token_iterator"
  - "std::tr1::regex_token_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_token_iterator 클래스[TR1]"
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
caps.latest.revision: 15
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# regex_token_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

부분 일치에 대한 반복기 클래스입니다.  
  
## 구문  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_token_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef sub_match<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const sub_match<BidIt> *pointer;  
    typedef const sub_match<BidIt>& reference;  
  
    regex_token_iterator();  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, int submatch = 0,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const std::vector<int> submatches,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    template<std::size_t N>  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const int (&submatches)[N],  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_token_iterator& right);  
    bool operator!=(const regex_token_iterator& right);  
    const basic_string<Elem>& operator*();  
    const basic_string<Elem> *operator->();  
    regex_token_iterator& operator++();  
    regex_token_iterator& operator++(int);  
private:  
    regex_iterator<BidIt, Elem, RXtraits> it; // exposition only  
    vector<int> subs;                         // exposition only  
    int pos;                                  // exposition only  
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
 템플릿 클래스는 일정한 정방향 반복기 개체를 설명합니다. 개념적으로 문자 시퀀스에서 정규식 일치를 검색하는 데 사용되는 `regex_iterator` 개체를 보관합니다. 각 정규식 일치에 대해 저장된 벡터 `subs`의 인덱스 값으로 식별된 부분 일치를 나타내는 `sub_match<BidIt>` 형식의 개체를 추출합니다.  
  
 인덱스 값 \-1은 이전 정규식 일치가 끝난 다음 바로 시작되거나 이전 정규식 일치가 없는 경우 문자 시퀀스의 시작에서 시작되고 현재 정규식 일치의 첫 번째 문자로 확장되지만 포함하지 않거나 현재 일치가 없는 경우 문자 시퀀스의 끝으로 확장되는 문자 시퀀스를 지정합니다. 다른 모든 인덱스 값 `idx`는 `it.match[idx]`에 보관된 캡처 그룹의 내용을 지정합니다.  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)   
 [regex\_iterator 클래스](../standard-library/regex-iterator-class.md)