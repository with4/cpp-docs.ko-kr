---
title: "underlying_type 클래스 | Microsoft Docs"
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
  - "underlying_type"
  - "std.underlying_type"
  - "std::underlying_type"
  - "type_traits/std::underlying_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underlying_type"
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# underlying_type 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

열거형 형식에 대 한 내부 정수 계열 형식을 생성합니다.  
  
## 구문  
  
```  
template <class T>  
    struct underlying_type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 `type` 템플릿 클래스의 멤버 typedef 이름을 내부 정수 계열 형식의 `T`, 때 `T` 가 열거형 형식인 없는 멤버 typedef 않으면 `type`합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)