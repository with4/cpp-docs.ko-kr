---
title: "&lt;regex&gt; | Microsoft Docs"
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
  - "<regex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex 헤더[TR1]"
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;regex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[정규식\(C\+\+\)](../standard-library/regular-expressions-cpp.md)을 구문 분석하는 템플릿 클래스와 텍스트에서 정규식 개체와 일치하는 항목을 검색하는 여러 템플릿 클래스 및 함수를 정의합니다.  
  
## 구문  
  
```  
#include <regex>  
```  
  
## 설명  
 정규식 개체를 만들려면 템플릿 클래스 [basic\_regex 클래스](../standard-library/basic-regex-class.md) 또는 해당 특수화 [regex Typedef](../Topic/regex%20Typedef.md) 및 [wregex Typedef](../Topic/wregex%20Typedef.md) 중 하나를 [regex\_constants::syntax\_option\_type](../Topic/regex_constants::syntax_option_type.md) 형식의 구문 플래그와 함께 사용합니다.  
  
 텍스트에서 정규식 개체와 일치하는 항목을 검색하려면 템플릿 함수 [regex\_match 함수](../Topic/regex_match%20Function.md) 및 [regex\_search 함수](../Topic/regex_search%20Function.md)를 [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 형식의 일치 플래그와 함께 사용합니다.  이러한 함수는 템플릿 클래스 [match\_results 클래스](../standard-library/match-results-class.md)와 해당 특수화 [cmatch Typedef](../Topic/cmatch%20Typedef.md), [wcmatch Typedef](../Topic/wcmatch%20Typedef.md), [smatch Typedef](../Topic/smatch%20Typedef.md) 및 [wsmatch Typedef](../Topic/wsmatch%20Typedef.md)를 템플릿 클래스 [sub\_match 클래스](../standard-library/sub-match-class.md)와 해당 특수화 [csub\_match Typedef](../Topic/csub_match%20Typedef.md), [wcsub\_match Typedef](../Topic/wcsub_match%20Typedef.md), [ssub\_match Typedef](../Topic/ssub_match%20Typedef.md) 및 [wssub\_match Typedef](../Topic/wssub_match%20Typedef.md)와 함께 사용하여 결과를 반환합니다.  
  
 정규식 개체와 일치하는 텍스트를 바꾸려면 템플릿 함수 [regex\_replace 함수](../Topic/regex_replace%20Function.md)를 [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 형식의 일치 플래그와 함께 사용합니다.  
  
 정규식 개체의 여러 일치 항목을 반복하려면 템플릿 클래스 [regex\_iterator 클래스](../standard-library/regex-iterator-class.md) 및 [regex\_token\_iterator 클래스](../standard-library/regex-token-iterator-class.md) 또는 해당 특수화 [cregex\_iterator Typedef](../Topic/cregex_iterator%20Typedef.md), [sregex\_iterator Typedef](../Topic/sregex_iterator%20Typedef.md), [wcregex\_iterator Typedef](../Topic/wcregex_iterator%20Typedef.md), [wsregex\_iterator Typedef](../Topic/wsregex_iterator%20Typedef.md), [cregex\_token\_iterator Typedef](../Topic/cregex_token_iterator%20Typedef.md), [sregex\_token\_iterator Typedef](../Topic/sregex_token_iterator%20Typedef.md), [wcregex\_token\_iterator Typedef](../Topic/wcregex_token_iterator%20Typedef.md) 또는 [wsregex\_token\_iterator Typedef](../Topic/wsregex_token_iterator%20Typedef.md) 중 하나를 [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 형식의 일치 플래그와 함께 사용합니다.  
  
 정규식의 문법에 대한 세부 정보를 수정하려면 정규식 특성을 구현하는 클래스를 작성합니다.  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_regex](../standard-library/basic-regex-class.md)|정규식을 래핑합니다.|  
|[match\_results](../standard-library/match-results-class.md)|부분 일치 시퀀스를 보유합니다.|  
|[regex\_constants](../standard-library/regex-constants-class.md)|분류된 상수를 보유합니다.|  
|[regex\_error](../standard-library/regex-error-class.md)|잘못된 정규식을 보고합니다.|  
|[regex\_iterator](../standard-library/regex-iterator-class.md)|일치 결과를 반복합니다.|  
|[regex\_traits](../standard-library/regex-traits-class.md)|일치를 위해 요소의 특징을 설명합니다.|  
|[regex\_traits\<char\>](../standard-library/regex-traits-char-class.md)|일치를 위해 `char`의 특징을 설명합니다.|  
|[regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)|일치를 위해 `wchar_t`의 특징을 설명합니다.|  
|[regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)|부분 일치를 반복합니다.|  
|[sub\_match](../standard-library/sub-match-class.md)|부분 일치를 설명합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[cmatch](../Topic/cmatch%20Typedef.md)|`char` `match_results`에 대한 형식 정의입니다.|  
|[cregex\_iterator](../Topic/cregex_iterator%20Typedef.md)|`char` `regex_iterator`에 대한 형식 정의입니다.|  
|[cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md)|`char` `regex_token_iterator`에 대한 형식 정의입니다.|  
|[csub\_match](../Topic/csub_match%20Typedef.md)|`char` `sub_match`에 대한 형식 정의입니다.|  
|[정규식](../Topic/regex%20Typedef.md)|`char` `basic_regex`에 대한 형식 정의입니다.|  
|[smatch](../Topic/smatch%20Typedef.md)|`string` `match_results`에 대한 형식 정의입니다.|  
|[sregex\_iterator](../Topic/sregex_iterator%20Typedef.md)|`string` `regex_iterator`에 대한 형식 정의입니다.|  
|[sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md)|`string` `regex_token_iterator`에 대한 형식 정의입니다.|  
|[ssub\_match](../Topic/ssub_match%20Typedef.md)|`string` `sub_match`에 대한 형식 정의입니다.|  
|[wcmatch](../Topic/wcmatch%20Typedef.md)|`wchar_t` `match_results`에 대한 형식 정의입니다.|  
|[wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md)|`wchar_t` `regex_iterator`에 대한 형식 정의입니다.|  
|[wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md)|`wchar_t` `regex_token_iterator`에 대한 형식 정의입니다.|  
|[wcsub\_match](../Topic/wcsub_match%20Typedef.md)|`wchar_t` `sub_match`에 대한 형식 정의입니다.|  
|[wregex](../Topic/wregex%20Typedef.md)|`wchar_t` `basic_regex`에 대한 형식 정의입니다.|  
|[wsmatch](../Topic/wsmatch%20Typedef.md)|`wstring` `match_results`에 대한 형식 정의입니다.|  
|[wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md)|`wstring` `regex_iterator`에 대한 형식 정의입니다.|  
|[wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md)|`wstring` `regex_token_iterator`에 대한 형식 정의입니다.|  
|[wssub\_match](../Topic/wssub_match%20Typedef.md)|`wstring` `sub_match`에 대한 형식 정의입니다.|  
  
### Functions  
  
|||  
|-|-|  
|[regex\_match](../Topic/regex_match%20Function.md)|정규식과 정확히 일치합니다.|  
|[regex\_replace](../Topic/regex_replace%20Function.md)|일치하는 정규식을 바꿉니다.|  
|[regex\_search](../Topic/regex_search%20Function.md)|정규식 일치 항목을 검색합니다.|  
|[스왑](../Topic/swap%20Function%20%3Cregex%3E.md)|`basic_regex` 또는 `match_results` 개체를 교환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자\=\=](../Topic/operator==%20%3Cregex%3E.md)|다양한 개체가 같은지 비교합니다.|  
|[operator\!\=](../Topic/operator!=%20%3Cregex%3E.md)|다양한 개체가 같지 않은지 비교합니다.|  
|[operator \<](../Topic/operator%3C%20%3Cregex%3E.md)|다양한 개체가 보다 작은지 비교합니다.|  
|[operator \<\=](../Topic/operator%3C=%20%3Cregex%3E.md)|다양한 개체가 보다 작거나 같은지 비교합니다.|  
|[operator \>](../Topic/operator%3E%20%3Cregex%3E.md)|다양한 개체가 보다 큰지 비교합니다.|  
|[operator \>\=](../Topic/operator%3E=%20%3Cregex%3E.md)|다양한 개체가 보다 크거나 같은지 비교합니다.|  
|[연산자 \<\<](../Topic/operator%3C%3C%20%3Cregex%3E.md)|스트림에 `sub_match`를 삽입합니다.|  
  
## 참고 항목  
 [정규식\(C\+\+\)](../standard-library/regular-expressions-cpp.md)