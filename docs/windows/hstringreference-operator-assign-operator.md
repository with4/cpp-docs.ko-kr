---
title: "HStringReference::Operator= 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 HStringReference 개체의 값을 현재 HStringReference 개체로 이동합니다.  
  
## 구문  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### 매개 변수  
 `other`  
 기존 HStringReference 개체입니다.  
  
## 설명  
 존재하는 `other` 개체의 값은 현재 HStringReference 개체에 복사되고 그때 `other` 개체는 소멸됩니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)