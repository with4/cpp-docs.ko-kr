---
title: "HStringReference::Operator&lt; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<"
dev_langs: 
  - "C++"
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator&lt; 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

첫 번째 매개변수가 두 번째 매개변수보다 적은지에 대한 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
  
```  
  
#### 매개 변수  
 `lhs`  
 비교할 첫 번째 매개변수입니다.  `lhs` 는 HStringReference에 대한 참조가 될 수 있습니다.  
  
 `rhs`  
 `rhs` 를 비교하기 위한 두 번째 매개변수는 HStringReference를 참조할 수 있습니다.  
  
## 반환 값  
 `lhs` 매개변수가 `rhs` 매개변수보다 적은 경우, `true`, 그렇지 않으면 `false`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)