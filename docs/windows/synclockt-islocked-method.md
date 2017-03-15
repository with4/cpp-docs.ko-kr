---
title: "SyncLockT::IsLocked 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked 메서드"
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockT::IsLocked 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
bool IsLocked() const;  
```  
  
## 반환 값  
 SyncLockT 개체가 잠겨 있으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
## 설명  
 현재 SyncLockT 개체 리소스이면 소유하고 있는지 여부를 나타냅니다. 즉, SyncLockT 개체는 *잠금*입니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [SyncLockT 클래스](../windows/synclockt-class.md)