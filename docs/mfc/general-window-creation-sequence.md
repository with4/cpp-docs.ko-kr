---
title: "일반 창 만들기 시퀀스 | Microsoft Docs"
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
  - "프레임 창[C++], 만들기"
  - "시퀀스[C++]"
  - "시퀀스[C++], 창 만들기"
  - "창[C++], 만들기"
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 일반 창 만들기 시퀀스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you create a window of your own, such as a child window, the framework uses much the same process as that described in [Document\/View Creation](../mfc/document-view-creation.md).  
  
 All the window classes provided by MFC employ [two\-stage construction](../mfc/one-stage-and-two-stage-construction-of-objects.md).  That is, during an invocation of the C\+\+ **new** operator, the constructor allocates and initializes a C\+\+ object but does not create a corresponding Windows window.  That is done afterward by calling the [Create](../Topic/CWnd::Create.md) member function of the window object.  
  
 The **Create** member function makes the Windows window and stores its `HWND` in the C\+\+ object's public data member [m\_hWnd](../Topic/CWnd::m_hWnd.md).  **Create** gives complete flexibility over the creation parameters.  Before calling **Create**, you may want to register a window class with the global function [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) in order to set the icon and class styles for the frame.  
  
 For frame windows, you can use the [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) member function instead of **Create**.  `LoadFrame` makes the Windows window using fewer parameters.  It gets many default values from resources, including the frame's caption, icon, accelerator table, and menu.  
  
> [!NOTE]
>  Your icon, accelerator table, and menu resources must have a common resource ID, such as **IDR\_MAINFRAME**, for them to be loaded by LoadFrame.  
  
## 추가 정보  
  
-   [Window objects](../mfc/window-objects.md)  
  
-   [Registering window "classes"](../mfc/registering-window-classes.md)  
  
-   [Destroying window objects](../mfc/destroying-window-objects.md)  
  
-   [Creating document frame windows](../mfc/creating-document-frame-windows.md)  
  
## 참고 항목  
 [창 만들기](../mfc/creating-windows.md)