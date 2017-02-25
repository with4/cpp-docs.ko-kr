---
title: "스크롤 막대 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SBS_VERT"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN"
  - "SBS_LEFTALIGN"
  - "SBS_RIGHTALIGN"
  - "SBS_TOPALIGN"
  - "SBS_SIZEBOXTOPLEFTALIGN"
  - "SBS_BOTTOMALIGN"
  - "SBS_SIZEBOX"
  - "SBS_HORZ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBS_BOTTOMALIGN 상수"
  - "SBS_HORZ 상수"
  - "SBS_LEFTALIGN 상수"
  - "SBS_RIGHTALIGN 상수"
  - "SBS_SIZEBOX 상수"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN 상수"
  - "SBS_SIZEBOXTOPLEFTALIGN 상수"
  - "SBS_TOPALIGN 상수"
  - "SBS_VERT 상수"
  - "스크롤 막대, 스타일"
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 스크롤 막대 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SBS\_BOTTOMALIGN** Used with the **SBS\_HORZ** style.  The bottom edge of the scroll bar is aligned with the bottom edge of the rectangle specified in the **Create** member function.  The scroll bar has the default height for system scroll bars.  
  
-   **SBS\_HORZ** Designates a horizontal scroll bar.  If neither the **SBS\_BOTTOMALIGN** nor **SBS\_TOPALIGN** style is specified, the scroll bar has the height, width, and position given in the **Create** member function.  
  
-   **SBS\_LEFTALIGN** Used with the **SBS\_VERT** style.  The left edge of the scroll bar is aligned with the left edge of the rectangle specified in the **Create** member function.  The scroll bar has the default width for system scroll bars.  
  
-   **SBS\_RIGHTALIGN** Used with the **SBS\_VERT** style.  The right edge of the scroll bar is aligned with the right edge of the rectangle specified in the **Create** member function.  The scroll bar has the default width for system scroll bars.  
  
-   **SBS\_SIZEBOX** Designates a size box.  If neither the **SBS\_SIZEBOXBOTTOMRIGHTALIGN** nor **SBS\_SIZEBOXTOPLEFTALIGN** style is specified, the size box has the height, width, and position given in the **Create** member function.  
  
-   **SBS\_SIZEBOXBOTTOMRIGHTALIGN** Used with the **SBS\_SIZEBOX** style.  The lower\-right corner of the size box is aligned with the lower\-right corner of the rectangle specified in the **Create** member function.  The size box has the default size for system size boxes.  
  
-   **SBS\_SIZEBOXTOPLEFTALIGN** Used with the **SBS\_SIZEBOX** style.  The upper\-left corner of the size box is aligned with the upper\-left corner of the rectangle specified in the **Create** member function.  The size box has the default size for system size boxes.  
  
-   **SBS\_SIZEGRIP** Same as **SBS\_SIZEBOX**, but with a raised edge.  
  
-   **SBS\_TOPALIGN** Used with the **SBS\_HORZ** style.  The top edge of the scroll bar is aligned with the top edge of the rectangle specified in the **Create** member function.  The scroll bar has the default height for system scroll bars.  
  
-   **SBS\_VERT** Designates a vertical scroll bar.  If neither the **SBS\_RIGHTALIGN** nor **SBS\_LEFTALIGN** style is specified, the scroll bar has the height, width, and position given in the **Create** member function.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../Topic/CScrollBar::Create.md)   
 [Scroll Bar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb787533)