---
title: "is_move_assignable 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_move_assignable"
  - "std.is_move_assignable"
  - "std::is_move_assignable"
  - "type_traits/std::is_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_assignable"
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# is_move_assignable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

테스트 형식을 사용할 수 있는 경우 이동 할당 합니다.  
  
## 구문  
  
```  
template<class T>  
    struct is_move_assignable;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식은 형식에 대 한 rvalue 참조 형식에 대 한 참조를 지정할 수 있는 경우 할당할 수 있는 이동 됩니다. 형식 조건자가 `is_assignable<T&, T&&>`합니다. 할당할 수 있는 유형에 만들겠습니다 스칼라 형식 및 클래스 형식은 컴파일러에서 생성 된 또는 사용자 정의 이동 할당 연산자를 이동 합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)