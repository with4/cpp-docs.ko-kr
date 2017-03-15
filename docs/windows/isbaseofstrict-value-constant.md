---
title: "IsBaseOfStrict::value 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict::value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value 상수"
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsBaseOfStrict::value 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## 설명  
 다른 기본 형식 인지 나타냅니다.  
  
 `value` 는 `true` 입니다, 이는 `Base` 이 `Derived` 형식의 기본 형식일 경우입니다. 그렇지 않으면 `false` 입니다.  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [IsBaseOfStrict 구조체](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)