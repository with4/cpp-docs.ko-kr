---
title: "CStatusBarCtrl 개체의 모드 설정 | Microsoft Docs"
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
  - "CStatusBarCtrl 클래스, 단순 및 비단순 모드"
  - "IsSimple 메서드, using"
  - "비단순 모드 및 상태 표시줄 컨트롤"
  - "SetSimple 메서드"
  - "단순 모드 및 상태 표시줄 컨트롤"
  - "상태 표시줄 컨트롤, 단순 및 비단순 모드"
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CStatusBarCtrl 개체의 모드 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

There are two modes for a `CStatusBarCtrl` object: simple and nonsimple.  In the majority of cases, your status bar control will have one or more parts, along with text and perhaps an icon or icons.  This is called the nonsimple mode.  For more information on this mode, see [Initializing the Parts of a CStatusBarCtrl Object](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 However, there are cases where you only need to display a single line of text.  In this case, the simple mode is sufficient for your needs.  To change the mode of the `CStatusBarCtrl` object to simple, make a call to the [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md) member function.  Once the status bar control is in simple mode, set the text by calling the **SetText** member function, passing 255 as the value for the **nPane** parameter.  
  
 You can use the [IsSimple](../Topic/CStatusBarCtrl::IsSimple.md) function to determine what mode the `CStatusBarCtrl` object is in.  
  
> [!NOTE]
>  If the status bar object is being changed from nonsimple to simple, or vice versa, the window is immediately redrawn and, if applicable, any defined parts are automatically restored.  
  
## 참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)