---
title: "is_trivially_copyable 클래스 | Microsoft Docs"
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
  - "is_trivially_copyable"
  - "std.is_trivially_copyable"
  - "std::is_trivially_copyable"
  - "type_traits/std::is_trivially_copyable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copyable"
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_trivially_copyable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 일반적으로 복사할 수 형식 인지 테스트 합니다.  
  
## 구문  
  
```  
template<class T>  
    struct is_trivially_copyable;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스 보관 하는 경우 true 형식을 `T` 형식인 일반적으로 복사할 수, 그렇지 않으면 false입니다. 형식은 일반적으로 복사할 수 있으며, 없는 특수 복사본 작업, 이동 작업 또는 소멸자 일반적으로 복사 작업으로 간주 됩니다 trivial 비트 복사본으로 구현할 수 있습니다. 일반적으로 복사할 수 있는 형식의 배열 및 기본 제공 형식을 사소 하 게 복사할 수 있습니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)