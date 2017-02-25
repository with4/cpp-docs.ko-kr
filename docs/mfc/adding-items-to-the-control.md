---
title: "컨트롤에 항목 추가 | Microsoft Docs"
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
  - "CListCtrl 클래스, 항목 추가"
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 컨트롤에 항목 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To add items to the list control \([CListCtrl](../mfc/reference/clistctrl-class.md)\), call one of several versions of the [InsertItem](../Topic/CListCtrl::InsertItem.md) member function, depending on what information you have.  One version takes a [LV\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) structure that you prepare.  Because the `LV_ITEM` structure contains numerous members, you have greater control over the attributes of the list control item.  
  
 Two important members \(in regard to the report view\) of the `LV_ITEM` structure are the `iItem` and `iSubItem` members.  The `iItem` member is the zero\-based index of the item the structure is referencing and the `iSubItem` member is the one\-based index of a subitem, or zero if the structure contains information about an item.  With these two members you determine, per item, the type and value of subitem information that is displayed when the list control is in report view.  For more information, see [CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md).  
  
 Additional members specify the item's text, icon, state, and item data. "Item data" is an application\-defined value associated with a list view item.  For more information about the `LV_ITEM` structure, see [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md).  
  
 Other versions of `InsertItem` take one or more separate values, corresponding to members in the `LV_ITEM` structure, allowing you to initialize only those members you want to support.  Generally, the list control manages storage for list items, but you can store some of the information in your application instead, using "callback items." For more information, see [Callback Items and the Callback Mask](../mfc/callback-items-and-the-callback-mask.md) in this topic and [Callback Items and the Callback Mask](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 For more information, see [Adding List\-View Items and Subitems](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)