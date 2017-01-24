---
title: "HString::Operator= 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator="
dev_langs: 
  - "C++"
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 HString 개체의 값을 현재 HString 개체로 이동합니다.  
  
## 구문  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
#### 매개 변수  
 `other`  
 기존 HString 개체  
  
## 설명  
 존재하는 `other` 개체의 값은 현재 HString 개체에 복사되고 그때 `other` 개체는 소멸됩니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)