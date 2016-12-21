---
title: "is_copy_assignable 클래스 | Microsoft Docs"
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
  - "is_copy_assignable"
  - "std.is_copy_assignable"
  - "std::is_copy_assignable"
  - "type_traits/std::is_copy_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_copy_assignable"
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_copy_assignable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

할당 시 형식을 복사할 수 있는지 여부를 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_copy_assignable;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 형식 `Ty`가 복사 할당 연산자를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.  is\_assignable\<Ty&, const Ty&\>과 동일합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)