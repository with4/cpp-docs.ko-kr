---
title: "대화 상자 닫기 | Microsoft Docs"
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
  - "대화 상자, 닫기"
  - "MFC 대화 상자, 닫기"
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 대화 상자 닫기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A modal dialog box closes when the user chooses one of its buttons, typically the OK button or the Cancel button.  Choosing the OK or Cancel button causes Windows to send the dialog object a **BN\_CLICKED** control\-notification message with the button's ID, either **IDOK** or **IDCANCEL**.  `CDialog` provides default handler functions for these messages: `OnOK` and `OnCancel`.  The default handlers call the `EndDialog` member function to close the dialog window.  You can also call `EndDialog` from your own code.  For more information, see the [EndDialog](../Topic/CDialog::EndDialog.md) member function of class `CDialog` in the *MFC Reference*.  
  
 To arrange for closing and deleting a modeless dialog box, override `PostNcDestroy` and invoke the **delete** operator on the **this** pointer.  [Destroying the Dialog Box](../mfc/destroying-the-dialog-box.md) explains what happens next.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)