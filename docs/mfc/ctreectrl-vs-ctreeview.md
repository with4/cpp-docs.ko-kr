---
title: "CTreeCtrl vs. CTreeView | Microsoft Docs"
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
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl 클래스, CTreeView 클래스와 비교"
  - "CTreeView 클래스, CTreeCtrl 클래스와 비교"
  - "트리 컨트롤, 및 트리 뷰"
  - "트리 뷰 컨트롤"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl vs. CTreeView
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC provides two classes that encapsulate tree controls: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) and [CTreeView](../mfc/reference/ctreeview-class.md).  Each class is useful in different situations.  
  
 Use `CTreeCtrl` when you need a plain child window control; for instance, in a dialog box.  You'd especially want to use `CTreeCtrl` if there will be other child controls in the window, as in a typical dialog box.  
  
 Use `CTreeView` when you want the tree control to act like a view window in document\/view architecture as well as a tree control.  A `CTreeView` will occupy the entire client area of a frame window or splitter window.  It will be automatically resized when its parent window is resized, and it can process command messages from menus, accelerator keys, and toolbars.  Since a tree control contains the data necessary to display the tree, the corresponding document object does not have to be complicated — you could even use [CDocument](../mfc/reference/cdocument-class.md) as the document type in your document template.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)