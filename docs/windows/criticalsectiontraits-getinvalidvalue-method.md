---
title: "CriticalSectionTraits::GetInvalidValue 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue 메서드"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits::GetInvalidValue 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CriticalSection 템플릿을 전문화한 결과 탬플릿은 항상 잘못됩니다.  
  
## 구문  
  
```  
inline static Type GetInvalidValue();  
```  
  
## 반환 값  
 항상 포인터를 잘못된 중요 섹션에 반환합니다.  
  
## 설명  
 *Type* 한정자는 `typedef CRITICAL_SECTION* Type;` 로서 정의됩니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)