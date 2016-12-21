---
title: "트리 컨트롤 항목 위치 | Microsoft Docs"
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
  - "CTreeCtrl 클래스, 항목 위치"
  - "트리 컨트롤의 항목 위치"
  - "위치, CTreeCtrl 항목"
  - "트리 컨트롤, 항목 위치"
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 트리 컨트롤 항목 위치
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An item's initial position is set when the item is added to the tree control \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) by using the `InsertItem` member function.  The member function call specifies the handle of the parent item and the handle of the item after which the new item is to be inserted.  The second handle must identify either a child item of the given parent or one of these values: `TVI_FIRST`, `TVI_LAST`, or `TVI_SORT`.  
  
 When `TVI_FIRST` or `TVI_LAST` is specified, the tree control places the new item at the beginning or end of the given parent item's list of child items.  When `TVI_SORT` is specified, the tree control inserts the new item into the list of child items in alphabetical order based on the text of the item labels.  
  
 You can put a parent item's list of child items into alphabetical order by calling the [SortChildren](../Topic/CTreeCtrl::SortChildren.md) member function.  This function includes a parameter that specifies whether all levels of child items descending from the given parent item are also sorted in alphabetical order.  
  
 The [SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md) member function allows you to sort child items based on criteria that you define.  When you call this function, you specify an application\-defined callback function that the tree control can call whenever the relative order of two child items needs to be decided.  The callback function receives two 32\-bit application\-defined values for the items being compared and a third 32\-bit value that you specify when calling `SortChildrenCB`.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)