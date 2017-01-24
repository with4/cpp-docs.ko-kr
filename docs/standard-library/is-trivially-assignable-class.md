---
title: "is_trivially_assignable 클래스 | Microsoft Docs"
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
  - "is_trivially_assignable"
  - "std.is_trivially_assignable"
  - "std::is_trivially_assignable"
  - "type_traits/std::is_trivially_assignable"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_assignable"
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_assignable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

값이 있는지 여부를 테스트 `From` 형식을에 게 할당할 수 `To` 형식  
  
## 구문  
  
```  
template <class To, class From>  
    struct is_trivially_assignable;  
```  
  
#### 매개 변수  
 후  
 할당을 받는 개체의 형식입니다.  
  
 보낸 사람  
 값을 제공하는 개체의 형식입니다.  
  
## 설명  
 식 `declval<To>() = declval<From>()` 제대로 구성 되어야 하며 특수 작업을 요구 하도록 컴파일러에 알 수 있어야 합니다. 둘 다 `From` 및 `To` 전체 형식 이어야 합니다 `void`, 또는 배열에 알 수 없는 바인딩.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)