---
title: "이벤트 싱크 맵 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 싱크 맵"
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 이벤트 싱크 맵
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

When an embedded OLE control fires an event, the control's container receives the event using a mechanism, called an "event sink map," supplied by MFC.  This event sink map designates handler functions for each specific event, as well as parameters of those events.  For more information on event sink maps, see the article [ActiveX Control Containers](../../mfc/activex-control-containers.md).  
  
### Event Sink Maps  
  
|||  
|-|-|  
|[BEGIN\_EVENTSINK\_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|Starts the definition of an event sink map.|  
|[DECLARE\_EVENTSINK\_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|Declares an event sink map.|  
|[END\_EVENTSINK\_MAP](../Topic/END_EVENTSINK_MAP.md)|Ends the definition of an event sink map.|  
|[ON\_EVENT](../Topic/ON_EVENT.md)|Defines an event handler for a specific event.|  
|[ON\_EVENT\_RANGE](../Topic/ON_EVENT_RANGE.md)|Defines an event handler for a specific event fired from a set of OLE controls.|  
|[ON\_EVENT\_REFLECT](../Topic/ON_EVENT_REFLECT.md)|Receives events fired by the control before they are handled by the control's container.|  
|[ON\_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|Defines a handler for handling property notifications from an OLE control.|  
|[ON\_PROPNOTIFY\_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|Defines a handler for handling property notifications from a set of OLE controls.|  
|[ON\_PROPNOTIFY\_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|Receives property notifications sent by the control before they are handled by the control's container.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)