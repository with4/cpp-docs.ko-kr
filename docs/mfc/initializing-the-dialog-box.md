---
title: "대화 상자 초기화 | Microsoft Docs"
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
  - "대화 상자 초기화"
  - "MFC 대화 상자, 초기화"
  - "모달 대화 상자, 초기화"
  - "모덜리스 대화 상자, 초기화"
  - "OnInitDialog 메서드"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 대화 상자 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

After the dialog box and all of its controls are created but just before the dialog box \(of either type\) appears on the screen, the dialog object's [OnInitDialog](../Topic/CDialog::OnInitDialog.md) member function is called.  For a modal dialog box, this occurs during the `DoModal` call.  For a modeless dialog box, `OnInitDialog` is called when **Create** is called.  You typically override `OnInitDialog` to initialize the dialog box's controls, such as setting the initial text of an edit box.  You must call the `OnInitDialog` member function of the base class, `CDialog`, from your `OnInitDialog` override.  
  
 If you want to set your dialog box's background color \(and that of all other dialog boxes in your application\), see [Setting the Dialog Box's Background Color](../mfc/setting-the-dialog-box’s-background-color.md).  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)