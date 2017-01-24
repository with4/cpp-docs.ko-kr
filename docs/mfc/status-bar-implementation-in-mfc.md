---
title: "MFC의 상태 표시줄 구현 | Microsoft Docs"
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
  - "COldStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COldStatusBar 클래스"
  - "CStatusBar 클래스, 및 CStatusBarCtrl 클래스"
  - "CStatusBar 클래스, 및 MFC 상태 표시줄"
  - "CStatusBarCtrl 클래스, 및 CStatusBar 클래스"
  - "CStatusBarCtrl 클래스, 및 MFC 상태 표시줄"
  - "상태 표시줄, 및 CStatusBarCtrl 클래스"
  - "상태 표시줄, 이전 버전과의 호환성"
  - "상태 표시줄, MFC에서 구현"
  - "상태 표시줄, COldStatusBar 클래스"
  - "상태 표시줄, Windows 95 구현"
  - "상태 표시기"
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC의 상태 표시줄 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A [CStatusBar](../mfc/reference/cstatusbar-class.md) object is a control bar with a row of text output panes.  The output panes are commonly used as message lines and as status indicators.  Examples include the menu help\-message lines that briefly explain the selected menu command and the indicators that show the status of the SCROLL LOCK, NUM LOCK, and other keys.  
  
 As of MFC version 4.0, status bars are implemented using class [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), which encapsulates a status bar common control.  For backward compatibility, MFC retains the older status bar implementation in class **COldStatusBar**.  The documentation for earlier versions of MFC describes **COldStatusBar** under `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), a member function new to MFC 4.0, allows you to take advantage of the Windows common control's support for status bar customization and additional functionality.  `CStatusBar` member functions give you most of the functionality of the Windows common controls; however, when you call `GetStatusBarCtrl`, you can give your status bars even more of the characteristics of a status bar.  When you call `GetStatusBarCtrl`, it will return a reference to a `CStatusBarCtrl` object.  You can use that reference to manipulate the status bar control.  
  
 The following figure shows a status bar that displays several indicators.  
  
 ![상태 표시줄](../mfc/media/vc37dy1.png "vc37DY1")  
상태 표시줄  
  
 Like the toolbar, the status\-bar object is embedded in its parent frame window and is constructed automatically when the frame window is constructed.  The status bar, like all control bars, is destroyed automatically as well when the parent frame is destroyed.  
  
## 추가 정보  
  
-   [Updating the text of a status bar pane](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC classes [CStatusBar](../mfc/reference/cstatusbar-class.md) and [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [Control bars](../mfc/control-bars.md)  
  
-   [Dialog bars](../mfc/dialog-bars.md)  
  
-   [Toolbars \(MFC Toolbar Implementation\)](../mfc/mfc-toolbar-implementation.md)  
  
## 참고 항목  
 [상태 표시줄](../mfc/status-bars.md)