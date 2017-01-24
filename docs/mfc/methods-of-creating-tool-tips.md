---
title: "도구 설명을 만드는 방법 | Microsoft Docs"
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
  - "CToolTipCtrl 클래스, 도구 설명 만들기"
  - "도구 설명[C++], 만들기"
  - "도구 설명[C++], 도구 설명 컨트롤"
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 설명을 만드는 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC provides three classes to create and manage the tool tip control: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) and [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md).  The tool tip member functions in these classes wrap the Windows common control API.  Class `CToolBarCtrl` and class `CToolTipCtrl` are derived from class `CWnd`.  
  
 `CWnd` provides four member functions to create and manage tool tips: [EnableToolTips](../Topic/CWnd::EnableToolTips.md), [CancelToolTips](../Topic/CWnd::CancelToolTips.md), [FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md), and [OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).  See these individual member functions for more information about how they implement tool tips.  
  
 If you create a toolbar using `CToolBarCtrl`, you can implement tool tips for that toolbar directly using the following member functions: [GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md) and [SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md).  See these individual member functions and [Handling Tool Tip Notifications](../mfc/handling-tool-tip-notifications.md) for more information about how they implement tool tips.  
  
 The `CToolTipCtrl` class provides the functionality of the Windows common tool tip control.  A single tool tip control can provide information for more than one tool.  A tool is either a window, such as a child window or control, or an application\-defined rectangular area within a window's client area.  The [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) class derives from `CToolTipCtrl` and provides additional visual styles and functionality.  
  
## 참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)