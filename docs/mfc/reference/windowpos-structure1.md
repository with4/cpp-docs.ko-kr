---
title: "WINDOWPOS 구조체 | Microsoft Docs"
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
  - "WINDOWPOS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPOS 구조체"
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WINDOWPOS 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `WINDOWPOS` structure contains information about the size and position of a window.  
  
## 구문  
  
```  
  
      typedef struct tagWINDOWPOS { /* wp */  
   HWND hwnd;  
   HWND hwndInsertAfter;  
   int x;  
   int y;  
   int cx;  
   int cy;  
   UINT flags;  
} WINDOWPOS;  
```  
  
#### 매개 변수  
 *hwnd*  
 Identifies the window.  
  
 *hwndInsertAfter*  
 Identifies the window behind which this window is placed.  
  
 *x*  
 Specifies the position of the left edge of the window.  
  
 *y*  
 Specifies the position of the right edge of the window.  
  
 `cx`  
 Specifies the window width, in pixels.  
  
 `cy`  
 Specifies the window height, in pixels.  
  
 `flags`  
 Specifies window\-positioning options.  This member can be one of the following values:  
  
-   **SWP\_DRAWFRAME** Draws a frame \(defined in the class description for the window\) around the window.  The window receives a `WM_NCCALCSIZE` message.  
  
-   **SWP\_FRAMECHANGED** Sends a `WM_NCCALCSIZE` message to the window, even if the window's size is not being changed.  If this flag is not specified, `WM_NCCALCSIZE` is sent only when the window's size is being changed.  
  
-   **SWP\_HIDEWINDOW** Hides the window.  
  
-   `SWP_NOACTIVATE` Does not activate the window.  
  
-   **SWP\_NOCOPYBITS** Discards the entire contents of the client area.  If this flag is not specified, the valid contents of the client area are saved and copied back into the client area after the window is sized or repositioned.  
  
-   `SWP_NOMOVE` Retains current position \(ignores the **x** and **y** members\).  
  
-   **SWP\_NOOWNERZORDER** Does not change the owner window's position in the Z\-order.  
  
-   `SWP_NOSIZE` Retains current size \(ignores the **cx** and **cy** members\).  
  
-   **SWP\_NOREDRAW** Does not redraw changes.  
  
-   **SWP\_NOREPOSITION** Same as **SWP\_NOOWNERZORDER**.  
  
-   **SWP\_NOSENDCHANGING** Prevents the window from receiving the `WM_WINDOWPOSCHANGING` message.  
  
-   `SWP_NOZORDER` Retains current ordering \(ignores the **hwndInsertAfter** member\).  
  
-   **SWP\_SHOWWINDOW** Displays the window.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)