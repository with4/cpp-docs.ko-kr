---
title: "is_nothrow_constructible 클래스 | Microsoft Docs"
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
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_constructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식을 생성 하 고 지정 된 인수 형식이 사용 되는 경우 throw 것으로 알려진 있는지 테스트 합니다.  
  
## 구문  
  
```  
template <class T, class... Args>  
    struct is_nothrow_constructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
 `Args`  
 생성자에서 일치 된 인수 형식과 `T`합니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 의 인수 형식과 사용 하 여 만들게 되며은 `Args`, 생성자 것으로 알려진 컴파일러에 의해 throw 하 고 그렇지 않으면 false 보유 합니다. 형식 `T` 생성 하는 경우 변수 정의 `T t(std::declval<Args>()...);` 이 제대로 구성 합니다. 둘 다 `T` 의 모든 형식 및 `Args` 완전 한 형식이 있어야 `void`, 또는 배열에 알 수 없는 바인딩.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)