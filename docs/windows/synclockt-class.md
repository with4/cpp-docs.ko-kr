---
title: "SyncLockT 클래스 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT 클래스"
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### 매개 변수  
 `SyncTraits`  
 리소스의 소유권을 가져올 수 있는 형식입니다.  
  
## 설명  
 단독으로 사용할 수 있는 형식을 나타내는 리소스의 소유권을 공유 합니다.  
  
 SyncLockT 클래스는, 예를 들어, [SRWLock](../windows/srwlock-class.md) 클래스를 구현을 돕습니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[SyncLockT::SyncLockT 생성자](../windows/synclockt-synclockt-constructor.md)|SyncLockT 클래스의 새 인스턴스를 초기화합니다.|  
|[SyncLockT::~SyncLockT 소멸자](../windows/synclockt-tilde-synclockt-destructor.md)|SyncLockT 클래스의 인스턴스를 초기화하지 않습니다.|  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[SyncLockT::SyncLockT 생성자](../windows/synclockt-synclockt-constructor.md)|SyncLockT 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SyncLockT::IsLocked 메서드](../windows/synclockt-islocked-method.md)|현재 SyncLockT 개체 리소스이면 소유하고 있는지 여부를 나타냅니다. 즉, SyncLockT 개체는 *잠금*입니다.|  
|[SyncLockT::Unlock 메서드](../windows/synclockt-unlock-method.md)|모든 경우에, 현재 syncLockT 개체에 의해 보유된 리소스의 컨트롤을 릴리스합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[SyncLockT::sync\_ 데이터 멤버](../windows/synclockt-sync-data-member.md)|SyncLockT 클래스에 의해 표시 되는 기본 리소스를 포함 합니다.|  
  
## 상속 계층  
 `SyncLockT`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock 클래스](../windows/srwlock-class.md)