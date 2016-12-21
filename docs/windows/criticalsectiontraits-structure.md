---
title: "CriticalSectionTraits 구조체 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSectionTraits 구조체"
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CriticalSection 개체를 중요한 부분을 해제하는 다른 잘못된 중요한 섹션 또는 함수를 지지하기 위해 전문적으로 합니다.  
  
## 구문  
  
```  
struct CriticalSectionTraits;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Type`|중요 섹션에 대한 포인터를 정의하는 `typedef` 입니다.  `Type`은 다음과 같이 정의됩니다. `typedef CRITICAL_SECTION* Type;`.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CriticalSectionTraits::GetInvalidValue 메서드](../windows/criticalsectiontraits-getinvalidvalue-method.md)|CriticalSection 템플릿을 전문화한 결과 탬플릿은 항상 잘못됩니다.|  
|[CriticalSectionTraits::Unlock 메서드](../windows/criticalsectiontraits-unlock-method.md)|중요 섹션 템플릿을 전문적으로 다룹니다. 그 결과, 지정된 중요한 섹션 개체의 소유권을 해제하는 것을 지원합니다.|  
  
## 상속 계층  
 `CriticalSectionTraits`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)