---
title: "HString::Operator!= 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator!="
dev_langs: 
  - "C++"
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator!= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 매개 변수가 같지 않은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
   inline bool operator!=(  
                  const HString& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HStringReference& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HStringReference& rhs) throw()  
  
inline bool operator!=(  
                  const HSTRING& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HSTRING& rhs) throw()  
  
```  
  
#### 매개 변수  
 `lhs`  
 비교할 첫 번째 매개변수입니다.  `lhs`HStringReference 개체 또는 HSTRING 핸들 또는 HString 일 수 있습니다.  
  
 `rhs`  
 `rhs` 를 비교할 두번째 매개변수는 HStrinReference 개체 또는 HSTRING 핸들 또는 HString입니다.  
  
## 반환 값  
 `lhs`와 `rhs` 매개 변수가 같지 않으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)