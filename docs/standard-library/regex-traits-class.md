---
title: "regex_traits 클래스 | Microsoft Docs"
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
  - "regex_traits"
  - "std::tr1::regex_traits"
  - "std.tr1.regex_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits 클래스[TR1]"
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# regex_traits 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일치를 위해 요소의 특징을 설명합니다.  
  
## 구문  
  
```  
template<class Elem>  
    struct regex_traits {  
    regex_traits();  
  
    static size_type length(const char_type *str);  
    char_type translate(char_type ch) const;  
    char_type translate_nocase(char_type ch) const;  
    template<class FwdIt>  
        string_type transform(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type transform_primary(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        char_class_type lookup_classname(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type lookup_collatename(FwdIt first, FwdIt last) const;  
    bool isctype(char_type ch, char_class_type cls) const;  
    int value(Elem ch, int base) const;  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
  
    typedef Elem char_type;  
    typedef T6 size_type;  
    typedef basic_string<Elem> string_type;  
    typedef T7 locale_type;  
    typedef T8 char_class_type;  
    };  
```  
  
#### 매개 변수  
 `Elem`  
 설명할 요소 형식입니다.  
  
## 설명  
 템플릿 클래스는 `Elem` 형식의 다양한 정규식 특성을 설명합니다. 템플릿 클래스 [basic\_regex 클래스](../standard-library/basic-regex-class.md)는 이 정보를 사용하여 `Elem` 형식의 요소를 조작합니다.  
  
 각 `regex_traits` 개체는 일부 멤버 함수에서 사용되는 `regex_traits::locale` 형식의 개체를 보유합니다. 기본 로캘은 `regex_traits::locale()`의 복사본입니다. 멤버 함수 `imbue`는 로캘 개체를 대체하고, 멤버 함수 `getloc`는 로캘 개체의 복사본을 반환합니다.  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits](../standard-library/regex-traits-class.md)   
 [regex\_traits \< char \> 클래스](../standard-library/regex-traits-char-class.md)   
 [regex\_traits\<wchar\_t\> 클래스](../standard-library/regex-traits-wchar-t-class.md)