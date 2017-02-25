---
title: "트리 컨트롤 항목 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[MFC], 항목 선택"
  - "CTreeCtrl 클래스, 항목 선택"
  - "트리 컨트롤의 항목 선택"
  - "트리 컨트롤, 항목 선택"
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 트리 컨트롤 항목 선택
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When the selection changes from one item to another, a tree control \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) sends [TVN\_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) and [TVN\_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) notification messages.  Both notifications include a value that specifies whether the change is the result of a mouse click or a keystroke.  The notifications also include information about the item that is gaining the selection and the item that is losing the selection.  You can use this information to set item attributes that depend on the selection state of the item.  Returning **TRUE** in response to **TVN\_SELCHANGING** prevents the selection from changing; returning **FALSE** allows the change.  
  
 An application can change the selection by calling the [SelectItem](../Topic/CTreeCtrl::SelectItem.md) member function.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)