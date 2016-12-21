---
title: "ModuleBase::DecrementObjectCount 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DecrementObjectCount 메서드"
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleBase::DecrementObjectCount 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
virtual long DecrementObjectCount() = 0;  
```  
  
## 반환 값  
 감소 연산 전에 수입니다.  
  
## 설명  
 구현될 때, 모듈에 의해 추적 되는 개체의 수를 감소시킵니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [ModuleBase 클래스](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)