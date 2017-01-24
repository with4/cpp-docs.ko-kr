---
title: "SRWLock::TryLockShared 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockShared 메서드"
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLock::TryLockShared 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 또는 지정 된 SRWLock 개체에 대한 공유 사용 모드로 SRWLock 개체를 얻으려고 합니다.  
  
## 구문  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### 매개 변수  
 `lock`  
 SRWLock개체에 대한 포인터  
  
## 반환 값  
 성공하면, 호출한 스레드가 공유 모드에서 SRWLock 개체의 잠금 소유권을 가져옵니다.  그렇지 않은 경우는 SRWLock 개체 상태가 올바르지 않습니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)