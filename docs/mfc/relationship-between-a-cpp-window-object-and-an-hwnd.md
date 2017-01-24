---
title: "C++ 창 개체와 HWND 간 관계 | Microsoft Docs"
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
  - "HWND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd 클래스, HWND"
  - "HWND"
  - "HWND, 창 개체"
  - "창 개체[C++], HWND 및"
  - "Windows 창[C++]"
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 창 개체와 HWND 간 관계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The window *object* is an object of the C\+\+ `CWnd` class \(or a derived class\) that your program creates directly.  It comes and goes in response to your program's constructor and destructor calls.  The Windows *window*, on the other hand, is an opaque handle to an internal Windows data structure that corresponds to a window and consumes system resources when present.  A Windows window is identified by a "window handle" \(`HWND`\) and is created after the `CWnd` object is created by a call to the **Create** member function of class `CWnd`.  The window may be destroyed either by a program call or by a user's action.  The window handle is stored in the window object's `m_hWnd` member variable.  The following figure shows the relationship between the C\+\+ window object and the Windows window.  Creating windows is discussed in [Creating Windows](../mfc/creating-windows.md).  Destroying windows is discussed in [Destroying Window Objects](../mfc/destroying-window-objects.md).  
  
 ![CWnd 창 개체 및 결과 창](../mfc/media/vc37fj1.png "vc37FJ1")  
창 개체 및 Windows 창  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)