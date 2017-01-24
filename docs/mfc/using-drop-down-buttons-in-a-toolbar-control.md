---
title: "도구 모음 컨트롤에서 드롭다운 단추 사용 | Microsoft Docs"
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
  - "TBN_DROPDOWN"
  - "TBSTYLE_EX_DRAWDDARROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl 클래스, 드롭다운 단추"
  - "도구 모음의 드롭다운 단추"
  - "TBN_DROPDOWN 알림"
  - "TBSTYLE_EX_DRAWDDARROWS"
  - "도구 모음[C++], 드롭다운 단추"
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 모음 컨트롤에서 드롭다운 단추 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In addition to standard push buttons, a toolbar can also have drop\-down buttons.  A drop\-down button is usually indicated by the presence of an attached down arrow.  
  
> [!NOTE]
>  The attached down arrow will appear only if the `TBSTYLE_EX_DRAWDDARROWS` extended style has been set.  
  
 When the user clicks on this arrow \(or the button itself, if no arrow is present\), a `TBN_DROPDOWN` notification message is sent to the parent of the toolbar control.  You can then handle this notification and display a pop\-up menu; similar to the behavior of Internet Explorer.  
  
 The following procedure illustrates how to implement a drop\-down toolbar button with a pop\-up menu:  
  
### To implement a drop\-down button  
  
1.  Once your `CToolBarCtrl` object has been created, set the `TBSTYLE_EX_DRAWDDARROWS` style, using the following code:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Set the `TBSTYLE_DROPDOWN` style for any new \([InsertButton](../Topic/CToolBarCtrl::InsertButton.md) or [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)\) or existing \([SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)\) buttons that will be drop\-down buttons.  The following example demonstrates modifying an existing button in a `CToolBarCtrl` object:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Add a `TBN_DROPDOWN` handler to the parent class of the toolbar object.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  In the new handler, display the appropriate popup menu.  The following code demonstrates one method:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## 참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)