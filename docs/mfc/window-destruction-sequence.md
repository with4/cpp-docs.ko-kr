---
title: "창 소멸 시퀀스 | Microsoft Docs"
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
  - "CWnd 개체, 소멸 시퀀스"
  - "소멸 창"
  - "소멸, windows"
  - "시퀀스[C++]"
  - "시퀀스[C++], 창 소멸"
  - "창[C++], 소멸"
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 창 소멸 시퀀스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In the MFC framework, when the user closes the frame window, the window's default [OnClose](../Topic/CWnd::OnClose.md) handler calls [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  The last member function called when the Windows window is destroyed is [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), which does some cleanup, calls the [Default](../Topic/CWnd::Default.md) member function to perform Windows cleanup, and lastly calls the virtual member function [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md).  The [CFrameWnd](../mfc/reference/cframewnd-class.md) implementation of `PostNcDestroy` deletes the C\+\+ window object.  
  
## 추가 정보  
  
-   [Allocating and deallocating window memory](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Detaching a CWnd from its HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## 참고 항목  
 [창 개체 소멸시키기](../mfc/destroying-window-objects.md)