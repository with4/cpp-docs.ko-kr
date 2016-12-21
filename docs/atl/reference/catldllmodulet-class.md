---
title: "CAtlDllModuleT Class | Microsoft Docs"
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
  - "ATL.CAtlDllModuleT"
  - "ATL::CAtlDllModuleT<T>"
  - "ATL::CAtlDllModuleT"
  - "ATL.CAtlDllModuleT<T>"
  - "CAtlDllModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlDllModuleT class"
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlDllModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 모듈을 DLL을 나타냅니다.  
  
## 구문  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlDllModuleT :  
   public CAtlModuleT< T >  
```  
  
#### 매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlDllModuleT`.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAtlDllModuleT::CAtlDllModuleT](../Topic/CAtlDllModuleT::CAtlDllModuleT.md)|생성자입니다.|  
|[CAtlDllModuleT::~CAtlDllModuleT](../Topic/CAtlDllModuleT::~CAtlDllModuleT.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAtlDllModuleT::DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md)|테스트 DLL을 로드할 수 없습니다.|  
|[CAtlDllModuleT::DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md)|클래스 팩터리를 반환합니다.|  
|[CAtlDllModuleT::DllMain](../Topic/CAtlDllModuleT::DllMain.md)|동적 연결 라이브러리 \(DLL\)의 선택적 진입점입니다.|  
|[CAtlDllModuleT::DllRegisterServer](../Topic/CAtlDllModuleT::DllRegisterServer.md)|DLL에서 개체에 대 한 시스템 레지스트리에 항목을 추가합니다.|  
|[CAtlDllModuleT::DllUnregisterServer](../Topic/CAtlDllModuleT::DllUnregisterServer.md)|DLL에서 개체에 대 한 시스템 레지스트리 항목을 제거합니다.|  
|[CAtlDllModuleT::GetClassObject](../Topic/CAtlDllModuleT::GetClassObject.md)|클래스 팩터리를 반환합니다.  호출 된  [다음에](../Topic/CAtlDllModuleT::DllGetClassObject.md).|  
  
## 설명  
 `CAtlDllModuleT`동적 연결 라이브러리 \(DLL\)의 모듈을 나타내며 모든 DLL 프로젝트에서 사용 하는 함수를 제공 합니다.  이 전문화의  [CAtlModuleT](../../atl/reference/catlmodulet-class.md) 클래스 등록에 대 한 지원이 포함 되어 있습니다.  
  
 Atl에서 모듈에 대 한 자세한 내용은  [ATL 모듈 클래스](../../atl/atl-module-classes.md).  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)