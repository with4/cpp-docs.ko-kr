---
title: "CMessageMap Class | Microsoft Docs"
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
  - "CMessageMap"
  - "ATL.CMessageMap"
  - "ATL::CMessageMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 메시지 처리기"
  - "CMessageMap class"
  - "message maps, ATL"
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMessageMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 다른 개체에 액세스 하는 개체의 메시지 맵 있습니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class ATL_NO_VTABLE CMessageMap  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMessageMap::ProcessWindowMessage](../Topic/CMessageMap::ProcessWindowMessage.md)|메시지 맵에 액세스 하는 `CMessageMap`\-클래스를 파생 합니다.|  
  
## 설명  
 `CMessageMap`다른 개체에 의해 액세스할 수 매핑합니다 개체의 메시지를 허용 하는 추상 기본 클래스입니다.  해당 메시지 맵을 노출 하는 개체에 대 한 순서에서 해당 클래스를 파생 해야 `CMessageMap`.  
  
 ATL을 사용 하 여 `CMessageMap` windows에 포함 된 지원 및 동적 메시지 맵 체인.  예를 들어, 모든 클래스를 포함 하는  [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개체에서 파생 해야 `CMessageMap`.  다음 코드에서 수행 되는  [SUBEDIT](../../top/visual-cpp-samples.md) 샘플.  \-  [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` 에서 자동으로 파생 클래스 `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/CPP/cmessagemap-class_1.h)]  
  
 때문에 포함 된 창에서 `m_EditCtrl`를 포함 하는 클래스에 메시지 맵을 사용 `CAtlEdit` 파생 `CMessageMap`.  
  
 메시지 맵에 대 한 자세한 내용은 참조 하십시오.  [메시지 맵](../../atl/message-maps-atl.md) 의 문서 "ATL 창 클래스"  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [CDynamicChain Class](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)