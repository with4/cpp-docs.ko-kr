---
title: "CFirePropNotifyEvent Class | Microsoft Docs"
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
  - "CFirePropNotifyEvent"
  - "ATL::CFirePropNotifyEvent"
  - "ATL.CFirePropNotifyEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFirePropNotifyEvent class"
  - "연결 지점[C++], notifying of events"
  - "sinks, notifying of ATL events"
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFirePropNotifyEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 컨트롤 속성의 변경 내용에 대 한 컨테이너의 싱크를 알리는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CFirePropNotifyEvent  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFirePropNotifyEvent::FireOnChanged](../Topic/CFirePropNotifyEvent::FireOnChanged.md)|\(정적\) 컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](../Topic/CFirePropNotifyEvent::FireOnRequestEdit.md)|\(정적\) 컨트롤 속성이 변경 되는 컨테이너의 싱크를 알립니다.|  
  
## 설명  
 `CFirePropNotifyEvent`컨트롤 속성 변경 되었거나 변경 되는 컨테이너의 싱크 알림 두 개의 메서드가 있습니다.  
  
 컨트롤을 구현 하는 클래스에서 파생 된 경우 `IPropertyNotifySink`, `CFirePropNotifyEvent` 메서드를 호출 하면 호출 `FireOnRequestEdit` 또는 `FireOnChanged`.  사용자 컨트롤 클래스에서 파생 되지 않은 경우 `IPropertyNotifySink`을 반환이 함수 호출을 `S_OK`.  
  
 컨트롤 만들기에 대 한 자세한 내용은  [ATL 자습서](../../atl/active-template-library-atl-tutorial.md).  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)