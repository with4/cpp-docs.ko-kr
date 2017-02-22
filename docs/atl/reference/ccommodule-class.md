---
title: "CComModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComModule class"
  - "DLL modules [C++], ATL"
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 7.0 기준으로 `CComModule` 사용 되지 않습니다: 참조  [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
class CComModule : public _ATL_MODULE  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComModule::GetClassObject](../Topic/CComModule::GetClassObject.md)|지정한 CLSID의 개체를 만듭니다.  Dll만.|  
|[CComModule::GetModuleInstance](../Topic/CComModule::GetModuleInstance.md)|`m_hInst`를 반환합니다.|  
|[CComModule::GetResourceInstance](../Topic/CComModule::GetResourceInstance.md)|`m_hInstResource`를 반환합니다.|  
|[CComModule::GetTypeLibInstance](../Topic/CComModule::GetTypeLibInstance.md)|`m_hInstTypeLib`를 반환합니다.|  
|[CComModule::Init](../Topic/CComModule::Init.md)|데이터 멤버를 초기화합니다.|  
|[CComModule::RegisterClassHelper](../Topic/CComModule::RegisterClassHelper.md)|개체의 표준 클래스 등록 시스템 레지스트리에 입력 합니다.|  
|[CComModule::RegisterClassObjects](../Topic/CComModule::RegisterClassObjects.md)|클래스 개체를 등록합니다.  Exe만.|  
|[CComModule::RegisterServer](../Topic/CComModule::RegisterServer.md)|개체 구조에서 각 개체에 대 한 시스템 레지스트리를 업데이트합니다.|  
|[CComModule::RegisterTypeLib](../Topic/CComModule::RegisterTypeLib.md)|형식 라이브러리를 등록합니다.|  
|[CComModule::RevokeClassObjects](../Topic/CComModule::RevokeClassObjects.md)|클래스 개체를 해지합니다.  Exe만.|  
|[CComModule::Term](../Topic/CComModule::Term.md)|데이터 멤버를 해제합니다.|  
|[CComModule::UnregisterClassHelper](../Topic/CComModule::UnregisterClassHelper.md)|개체의 표준 클래스 등록 시스템 레지스트리에서 제거합니다.|  
|[CComModule::UnregisterServer](../Topic/CComModule::UnregisterServer.md)|각 개체에는 오브젝트 맵이 등록을 취소 합니다.|  
|[CComModule::UpdateRegistryClass](../Topic/CComModule::UpdateRegistryClass.md)|등록 또는 등록 개체의 표준 클래스 등록을 취소 합니다.|  
|[CComModule::UpdateRegistryFromResourceD](../Topic/CComModule::UpdateRegistryFromResourceD.md)|등록 하거나 등록을 취소할 개체를 지정 된 리소스에 포함 된 스크립트를 실행 합니다.|  
|[CComModule::UpdateRegistryFromResourceS](../Topic/CComModule::UpdateRegistryFromResourceS.md)|ATL 레지스트리 구성 요소를 정적으로 링크 합니다.  등록 하거나 등록을 취소할 개체를 지정 된 리소스에 포함 된 스크립트를 실행 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComModule::m\_csObjMap](../Topic/CComModule::m_csObjMap.md)|개체 매핑 정보를 동기화 된 액세스를 보장합니다.|  
|[CComModule::m\_csTypeInfoHolder](../Topic/CComModule::m_csTypeInfoHolder.md)|형식 라이브러리 정보를 동기화 된 액세스를 보장합니다.|  
|[CComModule::m\_csWindowCreate](../Topic/CComModule::m_csWindowCreate.md)|동기화 액세스 클래스 정보 창 및 창 만들기에 사용 되는 정적 데이터를 확인 합니다.|  
|[CComModule::m\_hInst](../Topic/CComModule::m_hInst.md)|핸들 모듈 인스턴스를 포함합니다.|  
|[CComModule::m\_hInstResource](../Topic/CComModule::m_hInstResource.md)|기본적으로 모듈 인스턴스 핸들을 포함합니다.|  
|[CComModule::m\_hInstTypeLib](../Topic/CComModule::m_hInstTypeLib.md)|기본적으로 모듈 인스턴스 핸들을 포함합니다.|  
|[CComModule::m\_pObjMap](../Topic/CComModule::m_pObjMap.md)|모듈 인스턴스에 의해 유지 관리 되는 개체 맵 가리킵니다.|  
  
## 설명  
  
> [!NOTE]
>  이 클래스는 사용 되지 않습니다, 이제 ATL 코드 생성 마법사를 사용 하 고는  [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및  [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스.  참조  [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은.  ATL.의 이전 버전에서 만든 응용 프로그램 사용에 대 한 다음 정보를입니다.  `CComModule`여전히 ATL에 대 한 부분에는 이전 버전과 기능입니다.  
  
 `CComModule`모듈의 구성 요소에 액세스 하는 클라이언트가 COM 서버 모듈을 구현 합니다.  `CComModule`\(로컬\) 모듈 EXE와 DLL \(in\-process\)를 지원합니다.  
  
 A `CComModule` 인스턴스 클래스 개체 정의 유지 하는 개체 맵을 사용 합니다.  이 개체 맵을 배열로 구현 된 `_ATL_OBJMAP_ENTRY` 구조를 하 고 정보를 포함:  
  
-   입력 하 고 개체에 대 한 설명을 시스템 레지스트리에서 제거 합니다.  
  
-   클래스 팩터리를 통해 개체를 인스턴스화 합니다.  
  
-   구성 요소에서 루트 개체와 클라이언트 간의 통신을 설정합니다.  
  
-   클래스 개체의 수명 관리를 수행 합니다.  
  
 ATL COM 응용 프로그램 마법사를 실행할 때 마법사는 자동으로 생성 `_Module`, 전역 인스턴스를 `CComModule` 또는 여기에서 파생 된 클래스입니다.  ATL 프로젝트 마법사에 대 한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md).  
  
 이외에 `CComModule`, ATL 제공  [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), 아파트 모델 모듈 Exe 및 Windows 서비스를 구현 합니다.  파생 모듈에서 `CComAutoThreadModule` 여러 아파트에 개체를 만드는 데 사용할.  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## 요구 사항  
 `Header:`atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)