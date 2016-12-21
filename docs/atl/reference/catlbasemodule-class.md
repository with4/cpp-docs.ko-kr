---
title: "CAtlBaseModule Class | Microsoft Docs"
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
  - "ATL::CAtlBaseModule"
  - "ATL.CAtlBaseModule"
  - "CAtlBaseModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlBaseModule class"
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlBaseModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 모든 ATL 프로젝트에서 인스턴스화됩니다.  
  
## 구문  
  
```  
  
   class CAtlBaseModule :  
public _ATL_BASE_MODULE  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlBaseModule::CAtlBaseModule](../Topic/CAtlBaseModule::CAtlBaseModule.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlBaseModule::AddResourceInstance](../Topic/CAtlBaseModule::AddResourceInstance.md)|리소스 인스턴스 저장된 핸들이 목록에 추가합니다.|  
|[CAtlBaseModule::GetHInstanceAt](../Topic/CAtlBaseModule::GetHInstanceAt.md)|지정 된 리소스 인스턴스에 핸들을 반환합니다.|  
|[CAtlBaseModule::GetModuleInstance](../Topic/CAtlBaseModule::GetModuleInstance.md)|모듈 인스턴스에서 반환 된 `CAtlBaseModule` 개체.|  
|[CAtlBaseModule::GetResourceInstance](../Topic/CAtlBaseModule::GetResourceInstance.md)|리소스 인스턴스에서 반환 된 `CAtlBaseModule` 개체.|  
|[CAtlBaseModule::RemoveResourceInstance](../Topic/CAtlBaseModule::RemoveResourceInstance.md)|리소스 인스턴스 핸들을 저장된 목록에서 제거합니다.|  
|[CAtlBaseModule::SetResourceInstance](../Topic/CAtlBaseModule::SetResourceInstance.md)|리소스 인스턴스를 설정 하는 `CAtlBaseModule` 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlBaseModule::m\_bInitFailed](../Topic/CAtlBaseModule::m_bInitFailed.md)|모듈 초기화에 문제가 있는지를 나타내는 변수입니다.|  
  
## 설명  
 인스턴스를 `CAtlBaseModule` 명명 된 \_AtlBaseModule 모듈 인스턴스 핸들에 대 한 핸들 \(기본적으로 하나는 동일\) 리소스를 포함 하는 모듈 및 기본 리소스를 제공 하는 모듈 핸들의 배열에 포함 된 모든 ATL 프로젝트에서 제공 됩니다.  `CAtlBaseModule`안전 하 게 여러 스레드에서 액세스할 수 있습니다.  
  
 이 클래스는 사용 되지 않는 대체  [CComModule](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 되는 클래스  
  
## 상속 계층 구조  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md)  
  
 `CAtlBaseModule`  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)