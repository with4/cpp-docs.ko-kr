---
title: "is_rvalue_reference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_rvalue_reference"
  - "is_rvalue_reference"
  - "std::tr1::is_rvalue_reference"
  - "std.is_rvalue_reference"
  - "std::is_rvalue_reference"
  - "type_traits/std::is_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_rvalue_reference 클래스[TR1]"
  - "is_rvalue_reference"
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# is_rvalue_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 rvalue 참조인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_rvalue_reference;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 이 형식 조건자의 인스턴스는 `Ty` 형식이 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md) 참조인 경우 true입니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)