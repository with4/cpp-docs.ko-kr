---
title: "is_trivially_constructible 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_trivially_constructible"
  - "std.is_trivially_constructible"
  - "std::is_trivially_constructible"
  - "type_traits/std::is_trivially_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_constructible"
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_constructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 인수 형식을 사용 하는 경우 형식이 다르거나 일반적 만들게 되며 인지 테스트 합니다.  
  
## 구문  
  
```  
template <class T, class... Args>  
    struct is_trivially_constructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
 `Args`  
 생성자에서 일치 된 인수 형식과 `T`합니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 의 인수 형식과 사용 하 여 만들게 되며 사소 하 게 됩니다 `Args`, 그렇지 않으면 false 보유 합니다. 형식 `T` 사소 하 게 생성 하는 경우 변수 정의 `T t(std::declval<Args>()...);` 형식이 올바르고 없는 특수 작업을 호출 하 라고 합니다. 둘 다 `T` 의 모든 형식 및 `Args` 완전 한 형식이 있어야 `void`, 또는 배열에 알 수 없는 바인딩.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)