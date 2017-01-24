---
title: "regex_traits&lt;wchar_t&gt; 클래스 | Microsoft Docs"
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
  - "std::tr1::regex_traits<wchar_t>"
  - "regex_traits<wchar_t>"
  - "std.tr1.regex_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits<wchar_t> 클래스[TR1]"
ms.assetid: 288d6fdb-fb8e-4a4d-904a-53916be7f95b
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# regex_traits&lt;wchar_t&gt; 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

wchar\_t에 대한 regex\_traits의 특수화입니다.  
  
## 구문  
  
```  
template <>  
    class regex_traits<wchar_t>  
```  
  
## 설명  
 클래스는 `wchar_t` 형식의 요소에 대한 템플릿 클래스 [regex\_traits 클래스](../standard-library/regex-traits-class.md)의 명시적 특수화입니다\(이 형식의 개체를 조작하는 라이브러리 함수를 활용할 수 있도록 함\).  
  
## 요구 사항  
 **헤더:** \<regex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits 클래스](../standard-library/regex-traits-class.md)