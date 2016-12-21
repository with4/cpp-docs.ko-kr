---
title: "확장된 콤보 상자 컨트롤 만들기 | Microsoft Docs"
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
  - "CComboBoxEx 클래스, 확장된 콤보 상자 컨트롤 만들기"
  - "확장된 콤보 상자"
  - "확장된 콤보 상자, 만들기"
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 확장된 콤보 상자 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

How the extended combo box control is created depends on whether you are using the control in a dialog box or creating it in a nondialog window.  
  
### To use CComboBoxEx directly in a dialog box  
  
1.  In the dialog editor, add an Extended Combo Box control to your dialog template resource.  Specify its control ID.  
  
2.  Specify any styles required, using the Properties dialog box of the extended combo box control.  
  
3.  Use the [Add Member Variable Wizard](../ide/adding-a-member-variable-visual-cpp.md) to add a member variable of type [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) with the Control property.  You can use this member to call `CComboBoxEx` member functions.  
  
4.  Use the Properties window to map handler functions in the dialog class for any extended combo box control notification messages you need to handle \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md), set any additional styles for the `CComboBoxEx` object.  
  
### To use CComboBoxEx in a nondialog window  
  
1.  Define the control in the view or window class.  
  
2.  Call the control's [Create](../Topic/CTabCtrl::Create.md) member function, possibly in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), possibly as early as the parent window's [OnCreate](../Topic/CWnd::OnCreate.md) handler function.  Set the styles for the control.  
  
## 참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)