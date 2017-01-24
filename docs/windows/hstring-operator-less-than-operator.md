---
title: "HString::Operator&lt; 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator<"
dev_langs: 
  - "C++"
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator&lt; 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

첫 번째 매개변수가 두 번째 매개변수보다 적은지에 대한 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### 매개 변수  
 `lhs`  
 비교할 첫 번째 매개변수입니다.  `lhs` 는 HString에 대한 참조가 될 수 있습니다.  
  
 `rhs`  
 비교할 두 번째 매개변수입니다.  `rhs` 는 HString에 대한 참조가 될 수 있습니다.  
  
## 반환 값  
 `lhs` 매개변수가 `rhs` 매개변수보다 적은 경우, `true`, 그렇지 않으면 `false`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)