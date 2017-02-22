---
title: "SemaphoreTraits::Unlock 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock 메서드"
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SemaphoreTraits::Unlock 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공유 리소스의 버전 컨트롤입니다.  
  
## 구문  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### 매개 변수  
 `h`  
 세마포 개체에 대한 핸들입니다.  
  
## 설명  
 잠금 해제 작업을 성공적으로 없으면 Unlock\(\)는 실패의 원인을 나타내는 오류를 내보냅니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [SemaphoreTraits 구조체](../windows/semaphoretraits-structure.md)