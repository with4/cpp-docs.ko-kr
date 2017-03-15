---
title: "목록 컨트롤 만들기 | Microsoft Docs"
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
  - "CListCtrl 클래스, 컨트롤 만들기"
  - "list 컨트롤"
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 목록 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

How the list control \([CListCtrl](../mfc/reference/clistctrl-class.md)\) is created depends on whether you're using the control directly or using class [CListView](../mfc/reference/clistview-class.md) instead.  If you use `CListView`, the framework constructs the view as part of its document\/view creation sequence.  Creating the list view creates the list control as well \(the two are the same thing\).  The control is created in the view's [OnCreate](../Topic/CWnd::OnCreate.md) handler function.  In this case, the control is ready for you to add items, via a call to [GetListCtrl](../Topic/CListView::GetListCtrl.md).  
  
### To use CListCtrl directly in a dialog box  
  
1.  In the dialog editor, add a List Control to your dialog template resource.  Specify its control ID.  
  
2.  Use the [Add Member Variable Wizard](../ide/adding-a-member-variable-visual-cpp.md) to add a member variable of type `CListCtrl` with the Control property.  You can use this member to call `CListCtrl` member functions.  
  
3.  Use the Properties window to map handler functions in the dialog class for any list control notification messages you need to handle \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
4.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md), set the styles for the `CListCtrl`.  See [Changing List Control Styles](../mfc/changing-list-control-styles.md).  This determines the kind of "view" you get in the control, although you can change the view later.  
  
### To use CListCtrl in a nondialog window  
  
1.  Define the control in the view or window class.  
  
2.  Call the control's [Create](../Topic/CListCtrl::Create.md) member function, possibly in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), possibly as early as the parent window's [OnCreate](../Topic/CWnd::OnCreate.md) handler function \(if you're subclassing the control\).  Set the styles for the control.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)