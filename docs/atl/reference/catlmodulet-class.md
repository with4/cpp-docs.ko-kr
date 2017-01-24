---
title: "CAtlModuleT Class | Microsoft Docs"
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
  - "ATL::CAtlModuleT<T>"
  - "ATL.CAtlModuleT"
  - "ATL.CAtlModuleT<T>"
  - "ATL::CAtlModuleT"
  - "CAtlModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModuleT class"
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 ATL 모듈을 구현합니다.  
  
## 구문  
  
```  
  
      template <  
   class T   
>   
class ATL_NO_VTABLE CAtlModuleT :  
   public CAtlModule  
```  
  
#### 매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlModuleT`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlModuleT::CAtlModuleT](../Topic/CAtlModuleT::CAtlModuleT.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlModuleT::InitLibId](../Topic/CAtlModuleT::InitLibId.md)|현재 모듈의 GUID를 포함 하는 데이터 멤버를 초기화 합니다.|  
|[CAtlModuleT::RegisterAppId](../Topic/CAtlModuleT::RegisterAppId.md)|Exe 파일을 레지스트리에 추가 합니다.|  
|[CAtlModuleT::RegisterServer](../Topic/CAtlModuleT::RegisterServer.md)|서비스 레지스트리를 추가합니다.|  
|[CAtlModuleT::UnregisterAppId](../Topic/CAtlModuleT::UnregisterAppId.md)|Exe 파일을 레지스트리에서 제거합니다.|  
|[CAtlModuleT::UnregisterServer](../Topic/CAtlModuleT::UnregisterServer.md)|서비스를 제거합니다.|  
|[CAtlModuleT::UpdateRegistryAppId](../Topic/CAtlModuleT::UpdateRegistryAppId.md)|EXE 레지스트리 정보를 업데이트합니다.|  
  
## 설명  
 `CAtlModuleT`에서 파생 된  [CAtlModule](../../atl/reference/catlmodule-class.md), 실행 파일 \(EXE\) 또는 서비스 \(EXE\) ATL 모듈을 구현 합니다.  서비스 모듈은 Windows를 시작할 때 백그라운드에서 실행 되는 Windows 응용 프로그램 실행 모듈 로컬, 독립 프로세스 서버입니다.  
  
 `CAtlModuleT`초기화, 등록, 및 모듈의 등록을 취소를 지원 합니다.  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CAtlModule Class](../../atl/reference/catlmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)