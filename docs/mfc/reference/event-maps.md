---
title: "이벤트 맵 | Microsoft Docs"
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
  - "이벤트 맵"
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이벤트 맵
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Whenever a control wishes to notify its container that some action \(determined by the control developer\) has happened \(such as a keystroke, mouse click, or a change to the control's state\) it calls an event\-firing function.  This function notifies the control container that some important action has occurred by firing the related event.  
  
 The Microsoft Foundation Class Library offers a programming model optimized for firing events.  In this model, "event maps" are used to designate which functions fire which events for a particular control.  Event maps contain one macro for each event.  For example, an event map that fires a stock Click event might look like this:  
  
 [!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/CPP/event-maps_1.cpp)]  
  
 The **EVENT\_STOCK\_CLICK** macro indicates that the control will fire a stock Click event every time it detects a mouse click.  For a more detailed listing of other stock events, see the article [ActiveX Controls: Events](../../mfc/mfc-activex-controls-events.md).  Macros are also available to indicate custom events.  
  
 Although event\-map macros are important, you generally do not insert them directly.  This is because the Properties window automatically creates event\-map entries in your source files when you use it to associate event\-firing functions with events.  Any time you want to edit or add an event\-map entry, you can use the Properties window.  
  
 To support event maps, MFC provides the following macros:  
  
### Event Map Declaration and Demarcation  
  
|||  
|-|-|  
|[DECLARE\_EVENT\_MAP](../Topic/DECLARE_EVENT_MAP.md)|Declares that an event map will be used in a class to map events to event\-firing functions \(must be used in the class declaration\).|  
|[BEGIN\_EVENT\_MAP](../Topic/BEGIN_EVENT_MAP.md)|Begins the definition of an event map \(must be used in the class implementation\).|  
|[END\_EVENT\_MAP](../Topic/END_EVENT_MAP.md)|Ends the definition of an event map \(must be used in the class implementation\).|  
  
### Event Mapping Macros  
  
|||  
|-|-|  
|[EVENT\_CUSTOM](../Topic/EVENT_CUSTOM.md)|Indicates which event\-firing function will fire the specified event.|  
|[EVENT\_CUSTOM\_ID](../Topic/EVENT_CUSTOM_ID.md)|Indicates which event\-firing function will fire the specified event, with a designated dispatch ID.|  
  
### Message Mapping Macros  
  
|||  
|-|-|  
|[ON\_OLEVERB](../Topic/ON_OLEVERB.md)|Indicates a custom verb handled by the OLE control.|  
|[ON\_STDOLEVERB](../Topic/ON_STDOLEVERB.md)|Overrides a standard verb mapping of the OLE control.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)