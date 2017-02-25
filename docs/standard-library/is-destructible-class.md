---
title: "is_destructible 클래스 | Microsoft Docs"
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
  - "is_destructible"
  - "std.is_destructible"
  - "std::is_destructible"
  - "type_traits/std::is_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_destructible"
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# is_destructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 소멸 가능한지 테스트합니다.  
  
## 구문  
  
```  
template <class T>  
    struct is_destructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `T` 형식이 소멸 가능한 형식인 경우 true이고 그렇지 않은 경우 false입니다. 소멸 가능한 형식은 참조 형식, 개체 형식 및 `remove_all_extents_t<T>`와 같은 일부 `U` 형식의 경우 확인되지 않은 피연산자 `std::declval<U&>.~U()`가 올바르게 구성되는 경우의 형식입니다. 불완전한 형식, `void`, 및 함수 형식을 비롯한 기타 형식은 소멸 가능한 형식이 아닙니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)