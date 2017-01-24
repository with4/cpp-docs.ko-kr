---
title: "리스트 컨트롤의 작업 영역 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "list 컨트롤, 영역 작업"
  - "목록 컨트롤 영역 작업"
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 리스트 컨트롤의 작업 영역 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By default, a list control arranges all items in a standard grid fashion.  However, another method is supported, working areas, that arranges the list items into rectangular groups.  For an image of a list control that implements working areas, see Using List\-View Controls in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Working areas are visible only when the list control is in icon or small icon mode.  However, any current working areas are maintained if the view is switched to the report or list mode.  
  
 Working areas can be used to display an empty border \(on the left, top and\/or right of the items\), or cause a horizontal scroll bar to be displayed when there normally wouldn't be one.  Another common usage is to create multiple working areas to which items can be moved or dropped.  With this method, you could create areas in a single view that have different meanings.  The user could then categorize the items by placing them in a different area.  An example of this would be a view of a file system that has an area for read\/write files and another area for read\-only files.  If a file item were moved into the read\-only area, it would automatically become read\-only.  Moving a file from the read\-only area into the read\/write area would make the file read\/write.  
  
 `CListCtrl` provides several member functions for creating and managing working areas in your list control.  [GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md) and [SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md) retrieve and set an array of `CRect` objects \(or `RECT` structures\), which store the currently implemented working areas for your list control.  In addition, [GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md) retrieves the current number of working areas for your list control \(by default, zero\).  
  
## Items and Working Areas  
 When a working area is created, items that lie within the working area become members of it.  Similarly, if an item is moved into a working area, it becomes a member of the working area to which it was moved.  If an item does not lie within any working area, it automatically becomes a member of the first \(index 0\) working area.  If you want to create an item and have it placed within a specific working area, you will need to create the item and then move it into the desired working area with a call to [SetItemPosition](../Topic/CListCtrl::SetItemPosition.md).  The second example below demonstrates this technique.  
  
 The following example implements four working areas \(`rcWorkAreas`\), of equal size with a 10\-pixel\-wide border around each working area, in a list control \(`m_WorkAreaListCtrl`\).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_1.cpp)]  
  
 The call to [ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md) was made to get an estimate of the total area required to display all items in one region.  This estimate is then divided into four regions and padded with a 5\-pixel\-wide border.  
  
 The next example assigns the existing list items to each group \(`rcWorkAreas`\) and refreshes the control view \(`m_` `WorkAreaListCtrl`\) to complete the effect.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_2.cpp)]  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)