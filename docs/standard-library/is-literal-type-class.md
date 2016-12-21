---
title: "is_literal_type 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_literal_type"
  - "std.is_literal_type"
  - "std::is_literal_type"
  - "type_traits/std::is_literal_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_literal_type"
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_literal_type 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식으로 사용할 수 있는지 여부를 테스트 한 `constexpr` 변수 또는 생성에 사용 되거나에서 반환 된 `constexpr` 함수입니다.  
  
## 구문  
  
```  
template <class T>  
    struct is_literal_type;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 는 *리터럴 형식*, 를 그렇지 않으면 false 보유 합니다. 리터럴 형식이 `void`, 스칼라 형식, 참조 형식, 리터럴 형식의 배열 또는 클래스 리터럴 형식입니다. 리터럴 클래스 형식이 trivial 소멸자가 있는 클래스 형식, 집계 형식 되었거나 하나 이상의 비\-이동, 복사 `constexpr` 생성자와 모든 기본 클래스 및 비정적 데이터 멤버는 비휘발성 리터럴 형식입니다. 리터럴 형식 개념으로 컴파일러를 실행할 수 있는 모든 것을 포함 리터럴의 형식을 항상 리터럴 형식는 `constexpr` 컴파일 타임에 있습니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)