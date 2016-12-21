---
title: "HString::Attach 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::Attach"
dev_langs: 
  - "C++"
ms.assetid: 69451979-0014-4959-bc5c-1e4ab6fb28e4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Attach 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 HString 개체와 현재 HString 개체를 연결합니다.  
  
## 구문  
  
```  
  
void Attach(  
       HSTRING hstr  
       ) throw()  
```  
  
#### 매개 변수  
 `hstr`  
 기존 HString 개체  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)