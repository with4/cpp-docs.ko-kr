---
title: "is_trivially_copy_constructible 클래스 | Microsoft Docs"
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
  - "is_trivially_copy_constructible"
  - "std.is_trivially_copy_constructible"
  - "std::is_trivially_copy_constructible"
  - "type_traits/std::is_trivially_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_constructible"
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_constructible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에 trivial 복사 생성자가 있는지 테스트 합니다.  
  
## 구문  
  
```  
template<class T>  
    struct is_trivially_copy_constructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `T` 형식이 trivial 복사 생성자가 있는 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
 클래스에 대 한 복사 생성자를 `T` 선언 되는 경우 암시적으로, 클래스에는 간단 하지만 `T` 에 없는 가상 함수 또는 가상 기본 클래스의 모든 직접 자료 `T` trivial 복사 생성자가, 클래스 형식의 모든 비정적 데이터 멤버의 클래스는 trivial 복사 생성자 및 형식 배열 클래스의 모든 비정적 데이터 멤버의 클래스는 trivial 복사 생성자가 있습니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)