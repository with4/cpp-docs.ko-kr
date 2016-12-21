---
title: "CAtlModule Class | Microsoft Docs"
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
  - "ATL::CAtlModule"
  - "CAtlModule"
  - "ATL.CAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModule class"
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 여러 ATL 모듈 클래스에서 사용 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
   class ATL_NO_VTABLE CAtlModule :  
public _ATL_MODULE  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlModule::CAtlModule](../Topic/CAtlModule::CAtlModule.md)|생성자입니다.|  
|[CAtlModule::~CAtlModule](../Topic/CAtlModule::~CAtlModule.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlModule::AddCommonRGSReplacements](../Topic/CAtlModule::AddCommonRGSReplacements.md)|ATL 레지스트리 구성 요소 \(등록자\) 대체 지도에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.|  
|[CAtlModule::AddTermFunc](../Topic/CAtlModule::AddTermFunc.md)|새 모듈 종료 될 때 호출 될 함수를 추가 합니다.|  
|[CAtlModule::GetGITPtr](../Topic/CAtlModule::GetGITPtr.md)|전역 인터페이스 포인터를 반환합니다.|  
|[CAtlModule::GetLockCount](../Topic/CAtlModule::GetLockCount.md)|잠금 횟수를 반환합니다.|  
|[CAtlModule::Lock](../Topic/CAtlModule::Lock.md)|잠금 횟수를 늘립니다.|  
|[CAtlModule::Term](../Topic/CAtlModule::Term.md)|모든 데이터 멤버를 해제합니다.|  
|[CAtlModule::Unlock](../Topic/CAtlModule::Unlock.md)|잠금 횟수를 줄입니다.|  
|[CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md)|등록 하거나 등록을 취소할 개체를 지정 된 리소스에 포함 된 스크립트를 실행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](../Topic/CAtlModule::UpdateRegistryFromResourceDHelper.md)|이 메서드를 호출 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)|등록 하거나 등록을 취소할 개체를 지정 된 리소스에 포함 된 스크립트를 실행 합니다.  이 메서드는 정적으로 ATL 레지스트리 구성 요소에 연결합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlModule::m\_libid](../Topic/CAtlModule::m_libid.md)|현재 모듈의 GUID를 포함 합니다.|  
|[CAtlModule::m\_pGIT](../Topic/CAtlModule::m_pGIT.md)|전역 인터페이스 테이블에 대 한 포인터입니다.|  
  
## 설명  
 이 클래스를 사용 하 여  [CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md),  [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md), 및  [CAtlServiceModuleT 클래스](../../atl/reference/catlservicemodulet-class.md) 지원 DLL, EXE 응용 프로그램과 Windows 서비스에 각각 제공 합니다.  
  
 Atl에서 모듈에 대 한 자세한 내용은  [ATL 모듈 클래스](../../atl/atl-module-classes.md).  
  
 이 클래스는 사용 되지 않는 대체  [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 `CAtlModule`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)   
 [레지스트리 구성 요소\(등록자\)](../../atl/atl-registry-component-registrar.md)