---
title: "is_standard_layout 클래스 | Microsoft Docs"
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
  - "std.tr1.is_standard_layout"
  - "std::tr1::is_standard_layout"
  - "is_standard_layout"
  - "std.is_standard_layout"
  - "std::is_standard_layout"
  - "type_traits/std::is_standard_layout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_standard_layout 클래스[TR1]"
  - "is_standard_layout"
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_standard_layout 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 표준 레이아웃인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_standard_layout;  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Ty`|쿼리할 형식입니다.|  
  
## 설명  
 이 형식 조건자의 인스턴스는 `Ty` 형식이 메모리에 표준 레이아웃의 멤버 개체가 있는 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)