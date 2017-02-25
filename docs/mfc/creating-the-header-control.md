---
title: "헤더 컨트롤 만들기 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 만들기"
  - "헤더 컨트롤, 만들기"
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 헤더 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The header control is not directly available in the dialog editor \(although you can add a list control, which includes a header control\).  
  
### To put a header control in a dialog box  
  
1.  Manually embed a member variable of type [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) in your dialog class.  
  
2.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md), create and set the styles for the `CHeaderCtrl`, position it, and display it.  
  
3.  Add items to the header control.  
  
4.  Use the Properties window to map handler functions in the dialog class for any header\-control notification messages you need to handle \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
### To put a header control in a view \(not a CListView\)  
  
1.  Embed a [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) object in your view class.  
  
2.  Style, position, and display the header control window in the view's [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) member function.  
  
3.  Add items to the header control.  
  
4.  Use the Properties window to map handler functions in the view class for any header\-control notification messages you need to handle \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
 In either case, the embedded control object is created when the view or dialog object is created.  Then you must call [CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md) to create the control window.  To position the control, call [CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md) to determine the control's initial size and position and [SetWindowPos](../Topic/CWnd::SetWindowPos.md) to set the position you want.  Then add items as described in [Adding Items to the Header Control](../mfc/adding-items-to-the-header-control.md).  
  
 For more information, see [Creating a Header Control](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)