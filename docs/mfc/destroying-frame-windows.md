---
title: "프레임 창 소멸시키기 | Microsoft Docs"
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
  - "PostNcDestroy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Default 메서드"
  - "소멸 프레임 창"
  - "DestroyWindow 메서드"
  - "문서 프레임 창, 소멸"
  - "프레임 창[C++], 소멸"
  - "MFC[C++], 프레임 창"
  - "OnClose 메서드"
  - "OnNcDestroy 메서드, 및 프레임 창"
  - "PostNcDestroy 메서드"
  - "창[C++], 소멸"
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임 창 소멸시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The MFC framework manages window destruction as well as creation for those windows associated with framework documents and views.  If you create additional windows, you are responsible for destroying them.  
  
 In the framework, when the user closes the frame window, the window's default [OnClose](../Topic/CWnd::OnClose.md) handler calls [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  The last member function called when the Windows window is destroyed is [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), which does some cleanup, calls the [Default](../Topic/CWnd::Default.md) member function to perform Windows cleanup, and lastly calls the virtual member function [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md).  The [CFrameWnd](../mfc/reference/cframewnd-class.md) implementation of `PostNcDestroy` deletes the C\+\+ window object.  You should never use the C\+\+ **delete** operator on a frame window.  대신 `DestroyWindow`를 사용하십시오.  
  
 When the main window closes, the application closes.  If there are modified unsaved documents, the framework displays a message box to ask if the documents should be saved and ensures that the appropriate documents are saved if necessary.  
  
## 추가 정보  
  
-   [Creating document frame windows](../mfc/creating-document-frame-windows.md)  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)