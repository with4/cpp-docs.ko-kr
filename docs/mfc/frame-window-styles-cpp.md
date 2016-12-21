---
title: "프레임 창 스타일(C++) | Microsoft Docs"
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
  - "프레임 창[C++], 스타일"
  - "MFC[C++], 프레임 창"
  - "PreCreateWindow 메서드, 창 스타일 설정"
  - "스타일, windows"
  - "창 스타일[C++]"
  - "창[C++], MFC"
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: 8
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임 창 스타일(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The frame windows you get with the framework are suitable for most programs, but you can gain additional flexibility by using the advanced functions [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) and the MFC global function [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md).  `PreCreateWindow` is a member function of `CWnd`.  
  
 If you apply the **WS\_HSCROLL** and **WS\_VSCROLL** styles to the main frame window, they are instead applied to the **MDICLIENT** window so users can scroll the **MDICLIENT** area.  
  
 If the window's **FWS\_ADDTOTITLE** style bit is set \(which it is by default\), the view tells the frame window what title to display in the window's title bar based on the view's document name.  
  
## 추가 정보  
  
-   [Managing MDI child windows \(MDICLIENT\)](../mfc/managing-mdi-child-windows.md), the window within an MDI frame that contains the MDI child windows  
  
-   [Changing the styles of a window created by MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [창 스타일](../mfc/reference/window-styles.md)  
  
## 참고 항목  
 [프레임 창](../mfc/frame-windows.md)