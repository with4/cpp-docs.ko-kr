---
title: "SRWLockSharedTraits::Unlock 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock 메서드"
ms.assetid: 33cdead9-1900-4094-b18e-38fcf1a0bd28
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLockSharedTraits::Unlock 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 SRWLock 개체의 단독 제어를 해제합니다.  
  
## 구문  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### 매개 변수  
 `srwlock`  
 SRWLock 개체에 대한 핸들입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [SRWLockSharedTraits 구조체](../windows/srwlocksharedtraits-structure.md)