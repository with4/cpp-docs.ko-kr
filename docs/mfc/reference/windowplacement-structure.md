---
title: "WINDOWPLACEMENT 구조체 | Microsoft Docs"
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
  - "WINDOWPLACEMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPLACEMENT 구조체"
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WINDOWPLACEMENT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `WINDOWPLACEMENT` structure contains information about the placement of a window on the screen**.**  
  
## 구문  
  
```  
  
      typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
   UINT length;  
   UINT flags;  
   UINT showCmd;  
   POINT ptMinPosition;  
   POINT ptMaxPosition;  
   RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### 매개 변수  
 *length*  
 Specifies the length, in bytes, of the structure**.**  
  
 `flags`  
 Specifies flags that control the position of the minimized window and the method by which the window is restored.  This member can be one or both of the following flags:  
  
-   **WPF\_SETMINPOSITION** Specifies that the x\- and y\-positions of the minimized window can be specified**.** This flag must be specified if the coordinates are set in the **ptMinPosition** member.  
  
-   **WPF\_RESTORETOMAXIMIZED** Specifies that the restored window will be maximized, regardless of whether it was maximized before it was minimized.  This setting is valid only the next time the window is restored.  It does not change the default restoration behavior.  This flag is valid only when the **SW\_SHOWMINIMIZED** value is specified for the **showCmd** member.  
  
 *showCmd*  
 Specifies the current show state of the window.  This member can be one of the following values:  
  
-   **SW\_HIDE** Hides the window and passes activation to another window.  
  
-   **SW\_MINIMIZE** Minimizes the specified window and activates the top\-level window in the system's list.  
  
-   **SW\_RESTORE** Activates and displays a window.  If the window is minimized or maximized, Windows restores it to its original size and position \(same as **SW\_SHOWNORMAL**\).  
  
-   **SW\_SHOW** Activates a window and displays it in its current size and position.  
  
-   **SW\_SHOWMAXIMIZED** Activates a window and displays it as a maximized window.  
  
-   **SW\_SHOWMINIMIZED** Activates a window and displays it as an icon.  
  
-   **SW\_SHOWMINNOACTIVE** Displays a window as an icon.  The window that is currently active remains active.  
  
-   **SW\_SHOWNA** Displays a window in its current state.  The window that is currently active remains active.  
  
-   **SW\_SHOWNOACTIVATE** Displays a window in its most recent size and position.  The window that is currently active remains active.  
  
-   **SW\_SHOWNORMAL** Activates and displays a window.  If the window is minimized or maximized, Windows restores it to its original size and position \(same as **SW\_RESTORE**\).  
  
 *ptMinPosition*  
 Specifies the position of the window's top\-left corner when the window is minimized.  
  
 `ptMaxPosition`  
 Specifies the position of the window's top\-left corner when the window is maximized.  
  
 *rcNormalPosition*  
 Specifies the window's coordinates when the window is in the normal \(restored\) position.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)