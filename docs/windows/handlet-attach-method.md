---
title: "HandleT::Attach 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach 메서드"
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::Attach 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HandleT 개체와 지정된 된 핸들에 연결합니다.  
  
## 구문  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### 매개 변수  
 `h`  
 핸들입니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)