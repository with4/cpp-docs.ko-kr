---
title: "콜백 항목 및 콜백 마스크 | Microsoft Docs"
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
  - "CListCtrl 클래스의 콜백 항목"
  - "CListCtrl 클래스, 콜백 항목 및 콜백 마스크"
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 콜백 항목 및 콜백 마스크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For each of its items, a list view control typically stores the label text, the image list index of the item's icons, and a set of bit flags for the item's state.  You can define individual items as callback items, which are useful if your application already stores some of the information for an item.  
  
 You define an item as a callback item by specifying appropriate values for the `pszText` and `iImage` members of the **LV\_ITEM** structure \(see [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)\).  If the application maintains the item's or subitem's text, specify the **LPSTR\_TEXTCALLBACK** value for the `pszText` member.  If the application keeps track of the icon for the item, specify the **I\_IMAGECALLBACK** value for the `iImage` member.  
  
 In addition to defining callback items, you can also modify the control's callback mask.  This mask is a set of bit flags that specify the item states for which the application, rather than the control, stores the current data.  The callback mask applies to all of the control's items, unlike the callback item designation, which applies to a specific item.  The callback mask is zero by default, meaning that the control tracks all item states.  To change this default behavior, initialize the mask to any combination of the following values:  
  
-   `LVIS_CUT` The item is marked for a cut\-and\-paste operation.  
  
-   `LVIS_DROPHILITED` The item is highlighted as a drag\-and\-drop target.  
  
-   `LVIS_FOCUSED` The item has the focus.  
  
-   `LVIS_SELECTED` The item is selected.  
  
-   **LVIS\_OVERLAYMASK** The application stores the image list index of the current overlay image for each item.  
  
-   **LVIS\_STATEIMAGEMASK** The application stores the image list index of the current state image for each item.  
  
 For further information on retrieving and setting this mask, see [CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md) and [CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md).  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)