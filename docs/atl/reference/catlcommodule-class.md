---
title: "CAtlComModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlComModule"
  - "CAtlComModule"
  - "ATL::CAtlComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlComModule class"
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 서버 모듈을 구현합니다.  
  
## 구문  
  
```  
  
   class CAtlComModule :  
public _ATL_COM_MODULE  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlComModule::CAtlComModule](../Topic/CAtlComModule::CAtlComModule.md)|생성자입니다.|  
|[CAtlComModule::~CAtlComModule](../Topic/CAtlComModule::~CAtlComModule.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlComModule::RegisterServer](../Topic/CAtlComModule::RegisterServer.md)|개체 구조에서 각 개체에 대 한 시스템 레지스트리를 업데이트 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::RegisterTypeLib](../Topic/CAtlComModule::RegisterTypeLib.md)|형식 라이브러리를 등록 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::UnregisterServer](../Topic/CAtlComModule::UnregisterServer.md)|각 개체 맵에서 개체를 등록 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::UnRegisterTypeLib](../Topic/CAtlComModule::UnRegisterTypeLib.md)|형식 라이브러리를 등록 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CAtlComModule`모듈의 구성 요소에 액세스 하는 클라이언트가 COM 서버 모듈을 구현 합니다.  
  
 이 클래스는 사용 되지 않는 대체  [CComModule](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 되는 클래스  참조  [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)  
  
 `CAtlComModule`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)