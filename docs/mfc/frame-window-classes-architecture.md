---
title: "프레임 창 클래스(아키텍처) | Microsoft Docs"
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
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "프레임 창 클래스, 문서/뷰 아키텍처"
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임 창 클래스(아키텍처)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In document\/view architecture, frame windows are windows that contain a view window.  They also support having control bars attached to them.  
  
 In multiple document interface \(MDI\) applications, the main window is derived from `CMDIFrameWnd`.  It indirectly contains the documents' frames, which are `CMDIChildWnd` objects.  The `CMDIChildWnd` objects, in turn, contain the documents' views.  
  
 In single document interface \(SDI\) applications, the main window, derived from `CFrameWnd`, contains the view of the current document.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 The base class for an SDI application's main frame window.  Also the base class for all other frame window classes.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 The base class for an MDI application's main frame window.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 The base class for an MDI application's document frame windows.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Provides the frame window for a view when a server document is being edited in place.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)