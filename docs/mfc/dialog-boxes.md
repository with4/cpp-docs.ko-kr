---
title: "대화 상자 | Microsoft Docs"
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
  - "CDialog 클래스, MFC 대화 상자"
  - "MFC 대화 상자"
  - "MFC, 대화 상자"
  - "모달 대화 상자, MFC 대화 상자"
  - "모덜리스 대화 상자, MFC 대화 상자"
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Applications for Windows frequently communicate with the user through dialog boxes.  Class [CDialog](../mfc/reference/cdialog-class.md) provides an interface for managing dialog boxes, the Visual C\+\+ dialog editor makes it easy to design dialog boxes and create their dialog\-template resources, and Code wizards simplify the process of initializing and validating the controls in a dialog box and of gathering the values entered by the user.  
  
 Dialog boxes contain controls, including:  
  
-   Windows common controls such as edit boxes, pushbuttons, list boxes, combo boxes, tree controls, list controls, and progress indicators.  
  
-   ActiveX controls.  
  
-   Owner\-drawn controls: controls that you are responsible for drawing in the dialog box.  
  
 Most dialog boxes are modal, which require the user to close the dialog box before using any other part of the program.  But it is possible to create modeless dialog boxes, which let users work with other windows while the dialog box is open.  MFC supports both kinds of dialog box with class `CDialog`.  The controls are arranged and managed using a dialog\-template resource, created with the [dialog editor](../mfc/dialog-editor.md).  
  
 [Property sheets](../mfc/property-sheets-mfc.md), also known as tab dialog boxes, are dialog boxes that contain "pages" of distinct dialog\-box controls.  Each page has a file folder "tab" at the top.  Clicking a tab brings that page to the front of the dialog box.  
  
## 추가 정보  
  
-   [Example: Displaying a Dialog Box via a Menu Command](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [Dialog\-box components in the framework](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [Modal and modeless dialog boxes](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [Property sheets and property pages](../mfc/property-sheets-and-property-pages-mfc.md) in a dialog box  
  
-   [Creating the dialog resource](../mfc/creating-the-dialog-resource.md)  
  
-   [Creating a dialog class with Code Wizards](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [Life cycle of a dialog box](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [Dialog data exchange \(DDX\) and validation \(DDV\)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Type\-safe access to controls in a dialog box](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Mapping Windows messages to your class](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [Commonly Overridden Member Functions](../mfc/commonly-overridden-member-functions.md)  
  
-   [Commonly Added Member Functions](../mfc/commonly-added-member-functions.md)  
  
-   [Common dialog classes](../mfc/common-dialog-classes.md)  
  
-   [Dialog boxes in OLE](../mfc/dialog-boxes-in-ole.md)  
  
-   Create an application whose user interface is a dialog box: see the [CMNCTRL1](../top/visual-cpp-samples.md) or [CMNCTRL2](../top/visual-cpp-samples.md) sample programs.  The Application Wizard provides this option as well.  
  
-   [샘플](../mfc/dialog-sample-list.md)  
  
## 참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)