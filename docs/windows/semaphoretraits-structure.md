---
title: "SemaphoreTraits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SemaphoreTraits 구조체"
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SemaphoreTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

세마포 개체의 일반적인 특성을 정의합니다.  
  
## 구문  
  
```  
struct SemaphoreTraits : HANDLENullTraits;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SemaphoreTraits::Unlock 메서드](../windows/semaphoretraits-unlock-method.md)|공유 리소스의 버전 컨트롤입니다.|  
  
## 상속 계층  
 `HANDLENullTraits`  
  
 `SemaphoreTraits`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)