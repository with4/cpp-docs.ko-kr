---
title: "목록 컨트롤 및 목록 뷰 | Microsoft Docs"
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
  - "CListCtrl 클래스, 및 CListView"
  - "CListView 클래스, 및 CListCtrl"
  - "list 컨트롤, 목록 보기"
  - "목록 보기"
  - "뷰, 목록 및 목록 컨트롤"
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 목록 컨트롤 및 목록 뷰
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For convenience, MFC encapsulates the list control in two ways.  You can use list controls:  
  
-   Directly, by embedding a [CListCtrl](../mfc/reference/clistctrl-class.md) object in a dialog class.  
  
-   Indirectly, by using class [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView` makes it easy to integrate a list control with the MFC document\/view architecture, encapsulating the control much as [CEditView](../mfc/reference/ceditview-class.md) encapsulates an edit control: the control fills the entire surface area of an MFC view. \(The view *is* the control, cast to `CListView`.\)  
  
 A `CListView` object inherits from [CCtrlView](../mfc/reference/cctrlview-class.md) and its base classes and adds a member function to retrieve the underlying list control.  Use view members to work with the view as a view.  Use the [GetListCtrl](../Topic/CListView::GetListCtrl.md) member function to gain access to the list control's member functions.  Use these members to:  
  
-   Add, delete, or manipulate "items" in the list.  
  
-   Set or get list control attributes.  
  
 To obtain a reference to the `CListCtrl` underlying a `CListView`, call `GetListCtrl` from your list view class:  
  
 [!code-cpp[NVC_MFCListView#4](../mfc/codesnippet/CPP/list-control-and-list-view_1.cpp)]  
  
 This topic describes both ways to use the list control.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)