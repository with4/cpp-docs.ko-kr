---
title: "도구 설명 알림 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl 클래스, 알림 처리"
  - "알림, 도구 설명"
  - "도구 설명[C++], 알림"
  - "TOOLTIPTEXT 구조체"
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 도구 설명 알림 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you specify the `TBSTYLE_TOOLTIPS` style, the toolbar creates and manages a tool tip control.  A tool tip is a small pop\-up window that contains a line of text describing a toolbar button.  The tool tip is hidden, appearing only when the user puts the cursor on a toolbar button and leaves it there for approximately one\-half second.  The tool tip is displayed near the cursor.  
  
 Before the tool tip is displayed, the **TTN\_NEEDTEXT** notification message is sent to the toolbar's owner window to retrieve the descriptive text for the button.  If the toolbar's owner window is a `CFrameWnd` window, tool tips are displayed without any extra effort, because `CFrameWnd` has a default handler for the **TTN\_NEEDTEXT** notification.  If the toolbar's owner window is not derived from `CFrameWnd`, such as a dialog box or form view, you must add an entry to your owner window's message map and provide a notification handler in the message map.  The entry to your owner window's message map is as follows:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/CPP/handling-tool-tip-notifications_1.cpp)]  
  
## 설명  
 `memberFxn`  
 The member function to be called when text is needed for this button.  
  
 Note that the id of a tool tip is always 0.  
  
 In addition to the **TTN\_NEEDTEXT** notification, a tool tip control can send the following notifications to a toolbar control:  
  
|Notification|의미|  
|------------------|--------|  
|**TTN\_NEEDTEXTA**|Tool tip control requires ASCII text \(Windows 95 only\)|  
|**TTN\_NEEDTEXTW**|Tool tip control requires UNICODE text \(Windows NT only\)|  
|**TBN\_HOTITEMCHANGE**|Indicates that the hot \(highlighted\) item has changed.|  
|**NM\_RCLICK**|Indicates the user has right\-clicked a button.|  
|**TBN\_DRAGOUT**|Indicates the user has clicked the button and dragged the pointer off the button.  It allows an application to implement drag and drop from a toolbar button.  When receiving this notification, the application will begin the drag and drop operation.|  
|**TBN\_DROPDOWN**|Indicates the user has clicked a button that uses the **TBSTYLE\_DROPDOWN** style.|  
|**TBN\_GETOBJECT**|Indicates the user moved the pointer over a button that uses the **TBSTYLE\_DROPPABLE** style.|  
  
 For an example handler function and more information about enabling tool tips, see [Tool Tips](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
## 참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)