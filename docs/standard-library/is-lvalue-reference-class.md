---
title: "is_lvalue_reference 클래스 | Microsoft Docs"
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
  - "std.tr1.is_lvalue_reference"
  - "std::tr1::is_lvalue_reference"
  - "is_lvalue_reference"
  - "std.is_lvalue_reference"
  - "std::is_lvalue_reference"
  - "type_traits/std::is_lvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_lvalue_reference 클래스[TR1]"
  - "is_lvalue_reference"
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_lvalue_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 lvalue 참조인지 여부를 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_lvalue_reference;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 이 형식 조건자의 인스턴스는 형식 `Ty`가 개체나 함수에 대한 참조인 경우 true이고 그렇지 않은 경우 false입니다.  `Ty`가 rvalue 참조가 아닐 수 있습니다.  rvalue에 대한 자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)