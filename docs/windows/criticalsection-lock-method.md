---
title: "CriticalSection::Lock 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock 메서드"
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::Lock 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 임계 영역 개체를 소유할 때까지 기다립니다.  호출 스레드가 소유권을 부여하는 경우 함수를 반환 합니다.  
  
## 구문  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### 매개 변수  
 `cs`  
 임계 영역이 사용자가 지정한 개체입니다.  
  
## 반환 값  
 현재 임계 영역을 잠금을 해제하기 위해 사용할 수 있는 잠금 개체입니다.  
  
## 설명  
 첫 번째 **Lock** 함수는 현재 중요 섹션 개체에 영향을 줍니다.  두 번째 **Lock** 함수 사용자 지정 임계 영역에 영향을 줍니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)