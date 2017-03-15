---
title: "SRWLock::TryLockExclusive 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockExclusive 메서드"
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLock::TryLockExclusive 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 또는 지정 된 SRWLock 개체에 대 한 단독 사용 모드로 SRWLock 개체를 얻으려고 합니다.  호출이 성공한 경우, 호출 스레드는 잠금 소유권을 갖습니다.  
  
## 구문  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### 매개 변수  
 `lock`  
 SRWLock개체에 대한 포인터  
  
## 반환 값  
 성공하면, 호출한 스레드가 단독 모드에서 SRWLock 개체의 잠금 소유권을 가져옵니다.  그렇지 않은 경우는 SRWLock 개체 상태가 올바르지 않습니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)