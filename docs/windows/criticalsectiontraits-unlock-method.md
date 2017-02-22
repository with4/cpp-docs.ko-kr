---
title: "CriticalSectionTraits::Unlock 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock 메서드"
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSectionTraits::Unlock 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

중요 섹션 템플릿을 전문적으로 다룹니다. 그 결과, 지정된 중요한 섹션 개체의 소유권을 해제하는 것을 지원합니다.  
  
## 구문  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### 매개 변수  
 `cs`  
 임계 영역 개체에 대 한 포인터입니다.  
  
## 설명  
 *Type* 한정자는 `typedef CRITICAL_SECTION* Type;` 로서 정의됩니다.  
  
 자세한 내용은 "LeaveCriticalSection 함수" Windows API 설명서의 "동기화 기능" 섹션에 있습니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)