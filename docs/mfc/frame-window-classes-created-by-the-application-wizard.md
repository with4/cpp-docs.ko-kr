---
title: "응용 프로그램 마법사로 만든 프레임 창 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CMainFrame"
  - "CMainFrame::PreCreateWindow"
  - "CMainFrame.PreCreateWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 마법사[C++], 만든 프레임 창 클래스"
  - "CFrameWnd 클래스, 프레임 창"
  - "클래스[C++], 프레임 창"
  - "CMainFrame 클래스"
  - "CMDIChildWnd 클래스, 프레임 창"
  - "CMDIFrameWnd 클래스, 프레임 창"
  - "프레임 창 클래스, 응용 프로그램 마법사로 만들기"
  - "창 클래스"
  - "창 클래스, 프레임"
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# 응용 프로그램 마법사로 만든 프레임 창 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you use the [Application Wizard](../ide/creating-desktop-projects-by-using-application-wizards.md) to create a skeleton application, in addition to application, document, and view classes, the Application Wizard creates a derived frame\-window class for your application's main frame window.  The class is called `CMainFrame` by default, and the files that contain it are named MAINFRM.H and MAINFRM.CPP.  
  
 If your application is SDI, your `CMainFrame` class is derived from class [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 If your application is MDI, `CMainFrame` is derived from class [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md).  In this case `CMainFrame` implements the main frame, which holds the menu, toolbar, and status bars.  The Application Wizard does not derive a new document frame\-window class for you.  Instead, it uses the default implementation in [CMDIChildWnd Class](../mfc/reference/cmdichildwnd-class.md).  The MFC framework creates a child window to contain each view \(which can be of type `CScrollView`, `CEditView`, `CTreeView`, `CListView`, and so on\) that the application requires.  If you need to customize your document frame window, you can create a new document frame\-window class \(see [Adding a Class](../ide/adding-a-class-visual-cpp.md)\).  
  
 If you choose to support a toolbar, the class also has member variables of type [CToolBar](../mfc/reference/ctoolbar-class.md) and [CStatusBar](../mfc/reference/cstatusbar-class.md) and an `OnCreate` message\-handler function to initialize the two [control bars](../mfc/control-bars.md).  
  
 These frame\-window classes work as created, but to enhance their functionality, you must add member variables and member functions.  You may also want to have your window classes handle other Windows messages.  For more information, see [Changing the Styles of a Window Created by MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## 참고 항목  
 [프레임 창 클래스](../mfc/frame-window-classes.md)   
 [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/mfc-program-or-control-source-and-header-files.md)