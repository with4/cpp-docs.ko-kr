---
title: "SyncLockT::SyncLockT 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT, 생성자"
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockT::SyncLockT 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### 매개 변수  
 `other`  
 Rvalue\-참조 다른 SyncLockT 개체입니다.  
  
 `sync`  
 다른 SyncLockWithStatusT 개체에 대한 참조입니다.  
  
## 설명  
 SyncLockT 클래스의 새 인스턴스를 초기화합니다.  
  
 첫 번째 생성자는 현재 SyncLockT 개체 매개 변수에서 지정하는 다른 SyncLockT에서 `other`에 SyncLockT 개체를 무효화 합니다.  두 번째 생성자는 `protected`입니다, 유효 하지 않은 상태로 현재 SyncLockT 개체를 초기화 합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [SyncLockT 클래스](../windows/synclockt-class.md)