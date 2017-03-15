---
title: "SyncLockWithStatusT::SyncLockWithStatusT 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT, 생성자"
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SyncLockWithStatusT::SyncLockWithStatusT 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
#### 매개 변수  
 `other`  
 Rvalue\-참조 다른 SyncLockWithStatusT 개체입니다.  
  
 `sync`  
 다른 SyncLockWithStatusT 개체에 대한 참조입니다.  
  
 `status`  
 `other` 매개변수 또는 `sync` 매개변수의 [상태](../windows/synclockwithstatust-status-data-member.md) 데이터 멤버의 값입니다.  
  
## 설명  
 SyncLockWithStatusT 클래스의 새 인스턴스를 초기화합니다.  
  
 첫 번째 생성자는 현재 SyncLockWithStatusT 개체 매개 변수에서 지정 하는 다른 SyncLockWithStatusT에서 `other`에 SyncLockWithStatusT 개체를 무효화 합니다.  두 번째 생성자는 `protected`입니다, 유효 하지 않은 상태로 현재 SyncLockWithStatusT 개체를 초기화 합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus 메서드](../windows/synclockwithstatust-getstatus-method.md)