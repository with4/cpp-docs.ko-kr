---
title: "is_trivially_copy_assignable | Microsoft Docs"
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
  - "is_trivially_copy_assignable"
  - "std.is_trivially_copy_assignable"
  - "std::is_trivially_copy_assignable"
  - "type_traits/std::is_trivially_copy_assignable"
dev_langs: 
  - "C++"
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에 Trivial 복사 할당 연산자가 있는지 여부를 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_trivially_copy_constructible;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 형식 `Ty`가 Trivial 복사 할당 연산자를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.  
  
 클래스 `Ty`에 대한 할당 생성자는 다음과 같은 경우 Trivial입니다.  
  
 암시적으로 제공된 경우  
  
 클래스 `Ty`에 가상 함수가 없는 경우  
  
 클래스 `Ty`에 가상 기본이 없는 경우  
  
 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 할당 연산자가 있는 경우  
  
 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 할당 연산자가 있는 경우  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)