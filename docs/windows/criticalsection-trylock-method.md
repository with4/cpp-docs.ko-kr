---
title: "CriticalSection::TryLock 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLock 메서드"
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::TryLock 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

차단하지 않고 중요 섹션에 진입하려고 시도합니다.  호출이 성공한 경우, 호출 스레드는 중요 섹션의 소유권을 갖습니다.  
  
## 구문  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### 매개 변수  
 `cs`  
 임계 영역이 사용자가 지정한 개체입니다.  
  
## 반환 값  
 임계를 성공적으로 입력 하면 0이 아닌 값 또는 현재 스레드가 이미 임계 영역을 소유합니다.  다른 스레드가 임계 영역에 이미 소유하고 없으면 0입니다.  
  
## 설명  
 첫 번째 **TryLock** 함수는 현재 중요 섹션 개체에 영향을 줍니다.  두 번째 **TryLock** 함수 사용자 지정 임계 영역에 영향을 줍니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)