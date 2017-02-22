---
title: "basic_regex 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::basic_regex"
  - "basic_regex"
  - "std.tr1.basic_regex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_regex 클래스[TR1]"
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# basic_regex 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정규식을 래핑합니다.  
  
## 구문  
  
```  
template<class Elem,  
    class RXtraits = regex_traits<Elem>,  
    class basic_regex {  
public:  
    basic_regex();  
    explicit basic_regex(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    basic_regex(const basic_regex& right);  
    template<class STtraits, class STalloc>  
        explicit basic_regex(const basic_string<Elem, STtraits, STalloc>& str,  
            flag_type flags = ECMAScript);  
    template<class InIt>  
        explicit basic_regex(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    basic_regex& operator=(const basic_regex& right);  
    basic_regex& operator=(const Elem *ptr);  
    template<class STtraits, class STalloc>  
        basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);  
    basic_regex& assign(const basic_regex& right);  
    basic_regex& assign(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex& assign(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    template<class STtraits, class STalloc>  
    basic_regex& assign(const basic_string<Elem, STtraits, STalloc>& str,  
        flag_type flags = ECMAScript);  
    template<class InIt>  
        basic_regex& assign(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
    void swap(basic_regex& other) throw();  
    unsigned mark_count() const;  
    flag_type flags() const;  
  
    typedef Elem value_type;  
    typedef regex_constants::syntax_option_type flag_type;  
    typedef typename RXtraits::locale_type locale_type;  
    static const flag_type icase = regex_constants::icase;  
    static const flag_type nosubs = regex_constants::nosubs;  
    static const flag_type optimize = regex_constants::optimize;  
    static const flag_type collate = regex_constants::collate;  
    static const flag_type ECMAScript = regex_constants::ECMAScript;  
    static const flag_type basic = regex_constants::basic;  
    static const flag_type extended = regex_constants::extended;  
    static const flag_type awk = regex_constants::awk;  
    static const flag_type grep = regex_constants::grep;  
    static const flag_type egrep = regex_constants::egrep;  
private:  
    RXtraits traits;    // exposition only  
    };  
```  
  
#### 매개 변수  
 `Elem`  
 매칭할 요소의 형식입니다.  
  
 `RXtraits`  
 요소에 대한 특성 클래스입니다.  
  
## 설명  
 템플릿 클래스는 정규식을 포함하는 개체에 대해 설명합니다.  이 템플릿 클래스의 개체는 적절한 텍스트 문자열 인수와 함께 텍스트 함수 [regex\_match 함수](../Topic/regex_match%20Function.md), [regex\_search 함수](../Topic/regex_search%20Function.md) 및 [regex\_replace 함수](../Topic/regex_replace%20Function.md)로 전달하여 정규식과 일치하는 텍스트를 검색할 수 있습니다.  이 템플릿 클래스는 두 가지 특수화를 사용합니다. 즉, `char` 형식의 요소는 [regex Typedef](../Topic/regex%20Typedef.md) 형식 정의, `wchar_t` 형식의 요소는 [wregex Typedef](../Topic/wregex%20Typedef.md)를 적용합니다.  
  
 템플릿 인수 `RXtraits`는 템플릿 클래스가 지원하는 정규식 구문에 대해 다양하고 중요한 속성을 설명합니다.  이러한 정규식 특성을 지정하는 클래스는 템플릿 클래스 [regex\_traits 클래스](../standard-library/regex-traits-class.md)의 개체와 외부 인터페이스가 동일해야 합니다.  
  
 일부 함수는 정규식을 정의하는 피연산자 시퀀스를 사용합니다.  그러한 피연산자 시퀀스를 여러 방법으로 지정할 수 있습니다.  
  
 `ptr` \-\- `Elem`\(null 포인터는 안 됨\)에서 시작하고 null로 끝나는 시퀀스입니다\(예: 형식 `char`의 `ptr`의 경우 C 문자열\). 여기서 종료 요소는 값 `value_type()`이며 피연산자 시퀀스의 일부가 아닙니다.  
  
 `ptr`, `count` \-\- `count`\(null 포인터는 안 됨\)에서 시작하는 `ptr` 요소의 시퀀스  
  
 `str` \-\- `basic_string` 개체 `str`에서 지정한 시퀀스  
  
 `first`, `last` \-\- 범위 `first`에서 반복기 `last` 및 `[first, last)`에 의해 구분된 요소의 시퀀스  
  
 `right` \-\- `basic_regex` 개체 `right`  
  
 이러한 멤버 함수는 `flags` 형식에서 설명하는 것 이외에 정규식 해석을 위한 다양한 옵션을 지정하는 인수 `RXtraits`도 사용합니다.  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_match 함수](../Topic/regex_match%20Function.md)   
 [regex\_search 함수](../Topic/regex_search%20Function.md)   
 [regex\_replace 함수](../Topic/regex_replace%20Function.md)   
 [regex Typedef](../Topic/regex%20Typedef.md)   
 [wregex Typedef](../Topic/wregex%20Typedef.md)   
 [regex\_traits 클래스](../standard-library/regex-traits-class.md)