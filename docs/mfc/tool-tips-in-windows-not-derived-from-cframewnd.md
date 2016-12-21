---
title: "CFrameWnd에서 파생되지 않은 창의 도구 설명 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[MFC], 도구 설명"
  - "도구 설명을 사용하도록 설정"
  - "처리기 함수, 도구 설명"
  - "도움말, 컨트롤 도구 설명"
  - "TOOLTIPTEXT 구조체"
  - "TTN_NEEDTEXT 메시지"
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWnd에서 파생되지 않은 창의 도구 설명
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article family covers enabling tool tips for controls contained in a window that is not derived from [CFrameWnd](../mfc/reference/cframewnd-class.md).  The article [Toolbars Tool Tips](../mfc/toolbar-tool-tips.md) provides information about tool tips for controls in a `CFrameWnd`.  
  
 Topics covered in this article family include:  
  
-   [Enabling Tool Tips](../mfc/enabling-tool-tips.md)  
  
-   [Handling TTN\_NEEDTEXT Notification for Tool Tips](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [The TOOLTIPTEXT Structure](../mfc/tooltiptext-structure.md)  
  
 Tool tips are automatically displayed for buttons and other controls contained in a parent window derived from `CFrameWnd`.  This is because `CFrameWnd` has a default handler for the [TTN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) notification, which handles **TTN\_NEEDTEXT** notifications from tool tip controls associated with controls.  
  
 However, this default handler is not called when the **TTN\_NEEDTEXT** notification is sent from a tool tip control associated with a control in a window that is not a `CFrameWnd`, such as a control on a dialog box or a form view.  Therefore, it is necessary for you to provide a handler function for the **TTN\_NEEDTEXT** notification message in order to display tool tips for child controls.  
  
 The default tool tips provided for your windows by [CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md) do not have text associated with them.  To retrieve text for the tool tip to display, the **TTN\_NEEDTEXT** notification is sent to the tool tip control's parent window just before the tool tip window is displayed.  If there is no handler for this message to assign some value to the **pszText** member of the **TOOLTIPTEXT** structure, there will be no text displayed for the tool tip.  
  
## 참고 항목  
 [도구 설명](../mfc/tool-tips.md)