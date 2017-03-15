---
title: "CreatorMap::activationId 데이터 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap::activationId"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activationId 데이터 멤버"
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CreatorMap::activationId 데이터 멤버
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## 매개 변수  
 `clsid`  
 인터페이스 ID  
  
 `getRuntimeName`  
 Windows 런타임 개체의 이름을 검색하는 함수입니다.  
  
## 설명  
 개체 ID를 나타내는 기본 COM 클래스 ID를 통해 식별 되거나 또는 Windows 런타임 이름입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [CreatorMap 구조체](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)