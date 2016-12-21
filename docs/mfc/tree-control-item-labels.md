---
title: "트리 컨트롤 항목 레이블 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl 클래스, 항목 레이블"
  - "항목 레이블"
  - "항목 레이블, 트리 컨트롤"
  - "레이블, CTreeCtrl 항목"
  - "트리 컨트롤, 항목 레이블"
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 트리 컨트롤 항목 레이블
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You typically specify the text of an item's label when adding the item to the tree control \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  The `InsertItem` member function can pass a [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) structure that defines the item's properties, including a string containing the text of the label.  `InsertItem` has several overloads that can be called with various combinations of parameters.  
  
 A tree control allocates memory for storing each item; the text of the item labels takes up a significant portion of this memory.  If your application maintains a copy of the strings in the tree control, you can decrease the memory requirements of the control by specifying the **LPSTR\_TEXTCALLBACK** value in the **pszText** member of `TV_ITEM` or the `lpszItem` parameter instead of passing actual strings to the tree control.  Using **LPSTR\_TEXTCALLBACK** causes the tree control to retrieve the text of an item's label from the application whenever the item needs to be redrawn.  To retrieve the text, the tree control sends a [TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) notification message, which includes the address of a [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) structure.  You must respond by setting the appropriate members of the included structure.  
  
 A tree control uses memory allocated from the heap of the process that creates the tree control.  The maximum number of items in a tree control is based on the amount of memory available in the heap.  Each item takes 64 bytes.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)