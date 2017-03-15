---
title: "CreatorMap 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap"
  - "implements/Microsoft::WRL::Details::CreatorMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreatorMap 구조체"
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CreatorMap 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
struct CreatorMap;  
```  
  
## 설명  
 초기화, 등록 및 개체의 등록을 취소하는 방법에 대한 정보가 들어 있습니다.  
  
 CreatorMap은 다음 내용에 대해 설명합니다.  
  
-   초기화, 등록 및 개체의 등록을 취소 하는 방법.  
  
-   기본 COM에 따라 정품 인증 데이터를 비교 하는 방법 또는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 팩터리입니다.  
  
-   인터페이스에 대한 팩터리 캐시와 서버 이름에 대한 정보를 제공 합니다.  
  
## 멤버  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CreatorMap::activationId 데이터 멤버](../windows/creatormap-activationid-data-member.md)|개체 ID를 나타내는 기본 COM 클래스 ID를 통해 식별 되거나 또는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 이름입니다.|  
|[CreatorMap::factoryCache 데이터 멤버](../windows/creatormap-factorycache-data-member.md)|해당 CreatorMap에 대한 팩터리 캐시에 대한 포인터를 저장합니다.|  
|[CreatorMap::factoryCreator 데이터 멤버](../windows/creatormap-factorycreator-data-member.md)|지정 된 CreatorMap에 대한 팩터리를 만듭니다.|  
|[CreatorMap::serverName 데이터 멤버](../windows/creatormap-servername-data-member.md)|CreatorMap에 대한 서버 이름을 저장합니다.|  
  
## 상속 계층  
 `CreatorMap`  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)