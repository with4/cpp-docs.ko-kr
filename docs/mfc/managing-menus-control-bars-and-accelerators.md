---
title: "메뉴, 컨트롤 막대 및 액셀러레이터 관리 | Microsoft Docs"
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
  - "액셀러레이터 키 테이블[C++]"
  - "컨트롤 막대, 프레임 창에서 업데이트"
  - "프레임 창, 업데이트"
  - "MDI, 프레임 창"
  - "메뉴, 컨텍스트 변경으로 업데이트"
  - "메뉴 공유"
  - "상태 표시줄, 업데이트"
  - "사용자 인터페이스 개체 업데이트"
  - "사용자 인터페이스 개체, 업데이트"
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메뉴, 컨트롤 막대 및 액셀러레이터 관리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The frame window manages updating user\-interface objects, including menus, toolbar buttons, the status bar, and accelerators.  It also manages sharing the menu bar in MDI applications.  
  
## Managing Menus  
 The frame window participates in updating user\-interface items using the `ON_UPDATE_COMMAND_UI` mechanism described in [How to Update User\-Interface Objects](../mfc/how-to-update-user-interface-objects.md).  Buttons on toolbars and other control bars are updated during the idle loop.  Menu items in drop\-down menus on the menu bar are updated just before the menu drops down.  
  
 For MDI applications, the MDI frame window manages the menu bar and caption.  An MDI frame window owns one default menu that is used as the menu bar when there are no active MDI child windows.  When there are active children, the MDI frame window's menu bar is taken over by the menu for the active MDI child window.  If an MDI application supports multiple document types, such as chart and worksheet documents, each type puts its own menus into the menu bar and changes the main frame window's caption.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) provides default implementations for the standard commands on the Window menu that appears for MDI applications.  In particular, the New Window command \(**ID\_WINDOW\_NEW**\) is implemented to create a new frame window and view on the current document.  You need to override these implementations only if you need advanced customization.  
  
 Multiple MDI child windows of the same document type share menu resources.  If several MDI child windows are created by the same document template, they can all use the same menu resource, saving on system resources in Windows.  
  
## Managing the Status Bar  
 The frame window also positions the status bar within its client area and manages the status bar's indicators.  The frame window clears and updates the message area in the status bar as needed and displays prompt strings as the user selects menu items or toolbar buttons, as described in [How to Display Command Information in the Status Bar](../mfc/how-to-display-command-information-in-the-status-bar.md).  
  
## Managing Accelerators  
 Each frame window maintains an optional accelerator table that does keyboard accelerator translation for you automatically.  This mechanism makes it easy to define accelerator keys \(also called shortcut keys\) that invoke menu commands.  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)