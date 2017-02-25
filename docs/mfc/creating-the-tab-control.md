---
title: "탭 컨트롤 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TCS_EX_REGISTERDROP"
  - "TCS_EX_FLATSEPARATORS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl 클래스, 만들기"
  - "tab 컨트롤, 만들기"
  - "TCS_EX_FLATSEPARATORS 확장 스타일"
  - "TCS_EX_REGISTERDROP 확장 스타일"
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 탭 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

How the tab control is created depends on whether you are using the control in a dialog box or creating it in a nondialog window.  
  
### To use CTabCtrl directly in a dialog box  
  
1.  In the dialog editor, add a Tab Control to your dialog template resource.  Specify its control ID.  
  
2.  Use the [Add Member Variable Wizard](../ide/adding-a-member-variable-visual-cpp.md) to add a member variable of type [CTabCtrl](../mfc/reference/ctabctrl-class.md) with the Control property.  You can use this member to call `CTabCtrl` member functions.  
  
3.  Map handler functions in the dialog class for any tab control notification messages you need to handle.  자세한 내용은 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)을 참조하십시오.  
  
4.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md), set the styles for the `CTabCtrl`.  
  
### To use CTabCtrl in a nondialog window  
  
1.  Define the control in the view or window class.  
  
2.  Call the control's [Create](../Topic/CTabCtrl::Create.md) member function, possibly in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), possibly as early as the parent window's [OnCreate](../Topic/CWnd::OnCreate.md) handler function \(if you're subclassing the control\).  Set the styles for the control.  
  
 After the `CTabCtrl` object has been created, you can set or clear the following extended styles:  
  
-   **TCS\_EX\_FLATSEPARATORS** The tab control will draw separators between the tab items.  This extended style only affects tab controls that have the **TCS\_BUTTONS** and **TCS\_FLATBUTTONS** styles.  By default, creating the tab control with the **TCS\_FLATBUTTONS** style sets this extended style.  
  
-   **TCS\_EX\_REGISTERDROP** The tab control generates **TCN\_GETOBJECT** notification messages to request a drop target object when an object is dragged over the tab items in the control.  
  
    > [!NOTE]
    >  To receive the **TCN\_GETOBJECT** notification, you must initialize the OLE libraries with a call to [AfxOleInit](../Topic/AfxOleInit.md).  
  
 These styles can be retrieved and set, after the control has been created, with respective calls to the [GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md) and [SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md) member functions.  
  
 For instance, set the **TCS\_EX\_FLATSEPARATORS** style with the following lines of code:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/CPP/creating-the-tab-control_1.cpp)]  
  
 Clear the **TCS\_EX\_FLATSEPARATORS** style from a `CTabCtrl` object with the following lines of code:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/CPP/creating-the-tab-control_2.cpp)]  
  
 This will remove the separators that appear between the buttons of your `CTabCtrl` object.  
  
## 참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)