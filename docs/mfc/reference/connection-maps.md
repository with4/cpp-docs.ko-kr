---
title: "연결 맵 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
  - "연결 맵"
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연결 맵
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE controls are able to expose interfaces to other applications.  These interfaces only allow access from a container into that control.  If an OLE control wants to access external interfaces of other OLE objects, a connection point must be established.  This connection point allows a control outgoing access to external dispatch maps, such as event maps or notification functions.  
  
 The Microsoft Foundation Class Library offers a programming model that supports connection points.  In this model, "connection maps" are used to designate interfaces or connection points for the OLE control.  Connection maps contain one macro for each connection point.  For more information on connection maps, see the [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) class.  
  
 Typically, a control will support just two connection points: one for events and one for property notifications.  These are implemented by the `COleControl` base class and require no additional work by the control writer.  Any additional connection points you want to implement in your class must be added manually.  To support connection maps and points, MFC provides the following macros:  
  
### Connection Map Declaration and Demarcation  
  
|||  
|-|-|  
|[BEGIN\_CONNECTION\_PART](../Topic/BEGIN_CONNECTION_PART.md)|Declares an embedded class that implements an additional connection point \(must be used in the class declaration\).|  
|[END\_CONNECTION\_PART](../Topic/END_CONNECTION_PART.md)|Ends the declaration of a connection point \(must be used in the class declaration\).|  
|[CONNECTION\_IID](../Topic/CONNECTION_IID.md)|Specifies the interface ID of the control's connection point.|  
|[DECLARE\_CONNECTION\_MAP](../Topic/DECLARE_CONNECTION_MAP.md)|Declares that a connection map will be used in a class \(must be used in the class declaration\).|  
|[BEGIN\_CONNECTION\_MAP](../Topic/BEGIN_CONNECTION_MAP.md)|Begins the definition of a connection map \(must be used in the class implementation\).|  
|[END\_CONNECTION\_MAP](../Topic/END_CONNECTION_MAP.md)|Ends the definition of a connection map \(must be used in the class implementation\).|  
|[CONNECTION\_PART](../Topic/CONNECTION_PART.md)|Specifies a connection point in the control's connection map.|  
  
 The following functions assist a sink in establishing and disconnecting a connection using connection points:  
  
### Initialization\/Termination of Connection Points  
  
|||  
|-|-|  
|[AfxConnectionAdvise](../Topic/AfxConnectionAdvise.md)|Establishes a connection between a source and a sink.|  
|[AfxConnectionUnadvise](../Topic/AfxConnectionUnadvise.md)|Breaks a connection between a source and a sink.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)