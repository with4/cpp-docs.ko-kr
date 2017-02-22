---
title: "Microsoft::WRL::Wrappers::Details 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details"
  - "internal/Microsoft::WRL::Details"
  - "async/Microsoft::WRL::Details"
  - "corewrappers/Microsoft::WRL::Wrappers::Details"
  - "client/Microsoft::WRL::Details"
  - "module/Microsoft::WRL::Details"
  - "event/Microsoft::WRL::Details"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Details 네임스페이스"
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Microsoft::WRL::Wrappers::Details 네임스페이스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
namespace Microsoft::WRL::Wrappers::Details;  
```  
  
## 멤버  
  
### 클래스  
  
|Name|설명|  
|----------|--------|  
|[SyncLockT 클래스](../windows/synclockt-class.md)|단독으로 사용할 수 있는 형식을 나타내는 리소스의 소유권을 공유 합니다.|  
|[SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)|단독으로 사용할 수 있는 형식을 나타내는 리소스의 소유권을 공유 합니다.|  
  
### 메서드  
  
|Name|설명|  
|----------|--------|  
|[CompareStringOrdinal 메서드](../windows/comparestringordinal-method.md)|지정된 두 `HSTRING` 개체를 비교하고 정렬 순서에서 두 개체의 상대 위치를 나타내는 정수를 반환합니다.|  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)