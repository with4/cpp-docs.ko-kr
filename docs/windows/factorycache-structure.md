---
title: "FactoryCache 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FactoryCache 구조체"
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
struct FactoryCache;  
```  
  
## 설명  
 등록된 wrt 또는 COM 클래스 개체를 식별하는 클래스 팩터리의 위치와 값을 포함합니다.  
  
## 멤버  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[FactoryCache::cookie 데이터 멤버](../windows/factorycache-cookie-data-member.md)|등록을 식별하는 값이 포함된 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 COM 클래스 개체를 나중에 개체의 등록을 취소하는 데 사용합니다.|  
|[FactoryCache::factory 데이터 멤버](../windows/factorycache-factory-data-member.md)|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 COM 클래스 팩터리를 가르킵니다.|  
  
## 상속 계층  
 `FactoryCache`  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)