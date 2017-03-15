---
title: "CStatusBarCtrl을 사용하여 CStatusBarCtrl 개체 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl 클래스, 만들기"
  - "상태 표시줄 컨트롤, 만들기"
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CStatusBarCtrl을 사용하여 CStatusBarCtrl 개체 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Here is an example of a typical use of [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### To use a status bar control with parts  
  
1.  Construct the `CStatusBarCtrl` object.  
  
2.  Call [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md) if you want to set the minimum height of the status bar control's drawing area.  
  
3.  Call [SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md) to set the background color of the status bar control.  
  
4.  Call [SetParts](../Topic/CStatusBarCtrl::SetParts.md) to set the number of parts in a status bar control and the coordinate of the right edge of each part.  
  
5.  Call [SetText](../Topic/CStatusBarCtrl::SetText.md) to set the text in a given part of the status bar control.  The message invalidates the portion of the control that has changed, causing it to display the new text when the control next receives the `WM_PAINT` message.  
  
 In some cases, the status bar only needs to display a line of text.  In this case, make a call to [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  This puts the status bar control into "simple" mode, which displays a single line of text.  
  
## 참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)