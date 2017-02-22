---
title: "is_assignable 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_assignable"
  - "std.is_assignable"
  - "std::is_assignable"
  - "type_traits/std::is_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_assignable"
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# is_assignable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

값이 있는지 여부를 테스트 `From` 형식에 지정할 수는 `To` 유형입니다.  
  
## 구문  
  
```  
template <class To, class From>  
    struct is_assignable;  
```  
  
#### 매개 변수  
 후  
 할당을 받는 개체의 형식입니다.  
  
 보낸 사람  
 값을 제공하는 개체의 형식입니다.  
  
## 설명  
 확인 되지 않은 식 `declval<To>() = declval<From>()` 제대로 구성 되어야 합니다. 둘 다 `From` 및 `To` 전체 형식 이어야 합니다 `void`, 또는 배열에 알 수 없는 바인딩.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)