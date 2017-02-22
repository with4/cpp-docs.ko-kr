---
title: "sub_match 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sub_match"
  - "std::tr1::sub_match"
  - "std.tr1.sub_match"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sub_match 클래스[TR1]"
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sub_match 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

부분 일치를 설명합니다.  
  
## 구문  
  
```  
template<class BidIt>  
    class sub_match  
        : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;  
    int compare(const value_type *right) const;  
    difference_type length() const;  
    operator basic_string<value_type>() const;  
    basic_string<value_type> str() const;  
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
    };  
```  
  
#### 매개 변수  
 `BidIt`  
 부분 일치에 대한 반복기 형식입니다.  
  
## 설명  
 템플릿 클래스는 [regex\_match 함수](../Topic/regex_match%20Function.md) 또는 [regex\_search 함수](../Topic/regex_search%20Function.md) 호출에서 캡처 그룹과 일치하는 문자 시퀀스를 지정하는 개체에 대해 설명합니다.[match\_results 클래스](../standard-library/match-results-class.md) 형식의 개체는 검색에서 사용된 정규식의 각 캡처 그룹에 대해 하나씩 이러한 개체의 배열을 보유합니다.  
  
 캡처 그룹이 개체의 데이터 멤버와 일치하지 않는 경우 `matched`는 false를 보유하고 두 개의 반복기 `first`와 `second`\(기본 `std::pair`에서 상속됨\)가 동일합니다. 캡처 그룹이 일치하는 경우 `matched`는 true를 보유하고, 반복기 `first`는 캡처 그룹과 일치하는 대상 시퀀스의 첫 번째 문자를 가리키며, 반복기 `second`는 캡처 그룹과 일치하는 대상 시퀀스의 마지막 문자를 지난 한 위치를 가리킵니다. 멤버와 길이가 0인 일치의 경우 `matched`는 true를 보유하고, 두 개의 반복기가 동일하며, 둘 다 일치 항목의 위치를 가리킵니다.  
  
 길이가 0인 일치는 캡처 그룹이 어설션으로만 구성되거나 0 반복을 허용하는 반복으로 구성된 경우에 발생할 수 있습니다. 예:  
  
 "^"은 대상 시퀀스 "a"와 일치합니다. 즉, 캡처 그룹 0에 해당하는 `sub_match` 개체는 둘 다 시퀀스의 첫 번째 문자를 가리키는 반복기를 보유합니다.  
  
 "b\(a\*\)b"는 대상 시퀀스 "bb"와 일치합니다. 즉, 캡처 그룹 1에 해당하는 `sub_match` 개체는 둘 다 시퀀스의 두 번째 문자를 가리키는 반복기를 보유합니다.  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [sub\_match](../standard-library/sub-match-class.md)   
 [regex\_match 함수](../Topic/regex_match%20Function.md)   
 [regex\_search 함수](../Topic/regex_search%20Function.md)