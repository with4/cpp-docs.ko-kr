---
title: "is_trivially_destructible 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_trivially_destructible"
  - "std.is_trivially_destructible"
  - "std::is_trivially_destructible"
  - "type_traits/std::is_trivially_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_destructible"
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# is_trivially_destructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 다르거나 일반적 적인 인지 테스트 합니다.  
  
## 구문  
  
```  
template <class T>  
    struct is_trivially_destructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 파괴할 수 있는 형식이 며 소멸자 특수 작업을 사용 하 여 컴파일러에 알려져 있습니다. 그렇지 않으면 false 보유합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)