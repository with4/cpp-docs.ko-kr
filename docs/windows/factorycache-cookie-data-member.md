---
title: "FactoryCache::cookie 데이터 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache::cookie"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cookie 데이터 멤버"
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache::cookie 데이터 멤버
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## 설명  
 등록을 식별하는 값이 포함된 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 COM 클래스 개체를 나중에 개체의 등록을 취소하는 데 사용합니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [FactoryCache 구조체](../windows/factorycache-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)