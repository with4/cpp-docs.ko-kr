---
title: "is_nothrow_default_constructible 클래스 | Microsoft Docs"
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
  - "is_nothrow_default_constructible"
  - "std.is_nothrow_default_constructible"
  - "std::is_nothrow_default_constructible"
  - "type_traits/std::is_nothrow_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_default_constructible"
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_nothrow_default_constructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에 throw되지 않는 기본 생성자가 있는지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_nothrow_default_constructible;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식에 nothrow 기본 생성자가 있으면 true이고 그렇지 않으면 false입니다.  형식 조건자의 인스턴스는 `is_nothrow_constructible<Ty>`와 같습니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)