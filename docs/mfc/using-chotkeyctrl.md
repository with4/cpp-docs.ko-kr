---
title: "CHotKeyCtrl 사용 | Microsoft Docs"
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
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl 클래스, using"
  - "hot key 컨트롤"
  - "keys, hot 및 CHotKeyCtrl"
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHotKeyCtrl 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A hot key control, represented by class [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), is a window that displays a text representation of the key combination the user types into it, such as CTRL\+SHIFT\+Q.  It also maintains an internal representation of this key in the form of a virtual key code and a set of flags that represent the shift state.  The hot key control does not actually set the hot key — doing that is up to your program. \(For a list of standard virtual key codes, see Winuser.h.\)  
  
 Use a hot key control to get a user's input for which hot key to associate with a window or thread.  Hot key controls are often used in dialog boxes, such as you might display when asking the user to assign a hot key.  It is your program's responsibility to retrieve the values describing the hot key from the hot key control and to call the appropriate functions to associate the hot key with a window or thread.  
  
## 추가 정보  
  
-   [Using a Hot Key Control](../mfc/using-a-hot-key-control.md)  
  
-   [Setting a Hot Key](../mfc/setting-a-hot-key.md)  
  
-   [Global Hot Keys](../mfc/global-hot-keys.md)  
  
-   [Thread\-Specific Hot Keys](../mfc/thread-specific-hot-keys.md)  
  
## 참고 항목  
 [컨트롤](../mfc/controls-mfc.md)