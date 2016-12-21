---
title: "SRWLockExclusiveTraits 구조체 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockExclusiveTraits 구조체"
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단독 잠금 모드에서 SRWLock 클래스의 공통적인 특성을 설명합니다.  
  
## 구문  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Type`|[SRWLOCK](../windows/srwlock-class.md) 클래스에 대한 포인터 동의어입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SRWLockExclusiveTraits::GetInvalidValue 메서드](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|항상 유효 하지 않은 SRWLockExclusiveTraits 개체를 검색 합니다.|  
|[SRWLockExclusiveTraits::Unlock 메서드](../windows/srwlockexclusivetraits-unlock-method.md)|지정된 SRWLock 개체의 단독 제어를 해제합니다.|  
  
## 상속 계층  
 `SRWLockExclusiveTraits`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)