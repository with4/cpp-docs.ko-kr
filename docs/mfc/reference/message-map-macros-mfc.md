---
title: "메시지 맵 매크로(MFC) | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows 메시지 구분"
  - "메시지 맵 매크로"
  - "메시지 맵 범위"
  - "메시지 매핑 매크로"
  - "메시지 맵[C++], 선언 및 구분"
  - "메시지 맵[C++], 매크로"
  - "범위, 메시지 맵"
  - "Windows 메시지[C++], 선언"
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메시지 맵 매크로(MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

To support message maps, MFC supplies the following macros:  
  
### Message\-Map Declaration and Demarcation Macros  
  
|||  
|-|-|  
|[DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md)|Declares that a message map will be used in a class to map messages to functions \(must be used in the class declaration\).|  
|[BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md)|Begins the definition of a message map \(must be used in the class implementation\).|  
|[END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)|Ends the definition of a message map \(must be used in the class implementation\).|  
  
### Message\-Mapping Macros  
  
|||  
|-|-|  
|[ON\_COMMAND](../Topic/ON_COMMAND.md)|Indicates which function will handle a specified command message.|  
|[ON\_CONTROL](../Topic/ON_CONTROL.md)|Indicates which function will handle a specified control\-notification message.|  
|[ON\_MESSAGE](../Topic/ON_MESSAGE.md)|Indicates which function will handle a user\-defined message.|  
|[ON\_OLECMD](../Topic/ON_OLECMD.md)|Indicates which function will handle a menu command from a DocObject or its container.|  
|[ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md)|Indicates which function will handle a registered user\-defined message.|  
|[ON\_REGISTERED\_THREAD\_MESSAGE](../Topic/ON_REGISTERED_THREAD_MESSAGE.md)|Indicates which function will handle a registered user\-defined message when you have a `CWinThread` class.|  
|[ON\_THREAD\_MESSAGE](../Topic/ON_THREAD_MESSAGE.md)|Indicates which function will handle a user\-defined message when you have a `CWinThread` class.|  
|[ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)|Indicates which function will handle a specified user\-interface update command message.|  
  
### Message\-Map Range Macros  
  
|||  
|-|-|  
|[ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)|Indicates which function will handle the range of command IDs specified in the first two parameters to the macro.|  
|[ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)|Indicates which update handler will handle the range of command IDs specified in the first two parameters to the macro.|  
|[ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)|Indicates which function will handle notifications from the range of control IDs specified in the second and third parameters to the macro.  The first parameter is a control\-notification message, such as **BN\_CLICKED**.|  
  
 For more information on message maps, the message\-map declaration and demarcation macros, and the message\-mapping macros, see [Message Maps](../../mfc/reference/message-maps-mfc.md) and [Message Handling and Mapping Topics](../../mfc/message-handling-and-mapping.md).  For more information about message\-map ranges, see [Handlers for Message\-Map Ranges](../../mfc/handlers-for-message-map-ranges.md).  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)