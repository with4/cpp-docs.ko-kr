---
title: "ArgTraits::args 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraits::args"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "args 상수"
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ArgTraits::args 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
static const int args = -1; ;  
```  
  
## 설명  
 호출 메서드는 대리자 인터페이스에 매개 변수의 수를 유지합니다.  
  
## 설명  
 `args` \-1과 동등할 때, 호출 메서드 서명에 대해 일치 하지 않음을 나타냅니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [ArgTraits 구조체](../windows/argtraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)