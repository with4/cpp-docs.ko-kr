---
title: "프레임 창 클래스 | Microsoft Docs"
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
  - "클래스[C++], window"
  - "문서 프레임 창, 클래스"
  - "프레임 창 클래스"
  - "프레임 창 클래스, 프레임 창 클래스 정보"
  - "MDI[C++], 프레임 창"
  - "MFC[C++], 프레임 창"
  - "SDI(단일 문서 인터페이스), 프레임 창"
  - "창 클래스, 프레임"
  - "창[C++], MDI"
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 프레임 창 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Each application has one "main frame window," a desktop window that usually has the application name in its caption.  Each document usually has one "document frame window." A document frame window contains at least one view, which presents the document's data.  
  
## Frame Windows in SDI and MDI Applications  
 For an SDI application, there is one frame window derived from class [CFrameWnd](../mfc/reference/cframewnd-class.md).  This window is both the main frame window and the document frame window.  For an MDI application, the main frame window is derived from class [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), and the document frame windows, which are MDI child windows, are derived from class [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  
  
## Use the Frame\-Window Class, or Derive from It?  
 These classes provide most of the frame\-window functionality you need for your applications.  Under normal circumstances, the default behavior and appearance they provide will suit your needs.  If you need additional functionality, derive from these classes.  
  
### 추가 정보  
  
-   [Frame\-window classes created by the Application Wizard](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Frame\-window styles](../mfc/frame-window-styles-cpp.md)  
  
-   [Changing the styles of a window created by MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## 참고 항목  
 [프레임 창](../mfc/frame-windows.md)