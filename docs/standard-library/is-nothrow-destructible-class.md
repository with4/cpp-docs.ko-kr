---
title: "is_nothrow_destructible 클래스 | Microsoft Docs"
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
  - "is_nothrow_destructible"
  - "std.is_nothrow_destructible"
  - "std::is_nothrow_destructible"
  - "type_traits/std::is_nothrow_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_destructible"
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_destructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 적인 소멸자를 throw 컴파일러에 알려져 있는지 여부를 테스트 합니다.  
  
## 구문  
  
```  
template <class T>  
    struct is_nothrow_destructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 파괴할 수 있는 형식이 며 소멸자 것으로 알려진 컴파일러를 throw 합니다. 그렇지 않으면 false 보유합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)