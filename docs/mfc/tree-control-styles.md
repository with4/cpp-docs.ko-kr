---
title: "트리 컨트롤 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TVS_SINGLEEXPAND"
  - "TVS_LINESATROOT"
  - "TVS_HASBUTTONS"
  - "TVS_NOTOOLTIPS"
  - "TVS_HASLINES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl 클래스, 스타일"
  - "스타일, CTreeCtrl"
  - "스타일, 트리 컨트롤"
  - "트리 컨트롤, 스타일"
  - "TVS_EDITLABELS"
  - "TVS_HASBUTTONS"
  - "TVS_HASLINES"
  - "TVS_LINESATROOT"
  - "TVS_NOTOOLTIPS"
  - "TVS_SINGLEEXPAND"
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 트리 컨트롤 스타일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tree control \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) styles govern aspects of a tree control's appearance.  You set the initial styles when you create the tree control.  You can retrieve and change the styles after creating the tree control by using the [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) and [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows functions, specifying **GWL\_STYLE** for the `nIndex` parameter.  For a complete list of styles, see [Tree View Control Window Styles](http://msdn.microsoft.com/library/windows/desktop/bb760013) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 The **TVS\_HASLINES** style enhances the graphic representation of a tree control's hierarchy by drawing lines that link child items to their corresponding parent item.  This style does not link items at the root of the hierarchy.  To do so, you need to combine the **TVS\_HASLINES** and **TVS\_LINESATROOT** styles.  
  
 The user can expand or collapse a parent item's list of child items by double\-clicking the parent item.  A tree control that has the **TVS\_SINGLEEXPAND** style causes the item being selected to expand and the item being unselected to collapse.  If the mouse is used to single\-click the selected item and that item is closed, it will be expanded.  If the selected item is single\-clicked when it is open, it will be collapsed.  
  
 A tree control that has the **TVS\_HASBUTTONS** style adds a button to the left side of each parent item.  The user can click the button to expand or collapse the child items as an alternative to double\-clicking the parent item.  **TVS\_HASBUTTONS** does not add buttons to items at the root of the hierarchy.  To do so, you must combine **TVS\_HASLINES**, **TVS\_LINESATROOT**, and **TVS\_HASBUTTONS**.  
  
 The **TVS\_EDITLABELS** style makes it possible for the user to edit the labels of tree control items.  For more information about editing labels, see [Tree Control Label Editing](../mfc/tree-control-label-editing.md) later in this topic.  
  
 The **TVS\_NOTOOLTIPS** style disables the automatic tool tip feature of tree view controls.  This feature automatically displays a tool tip, containing the title of the item under the mouse cursor, if the entire title is not currently visible.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)