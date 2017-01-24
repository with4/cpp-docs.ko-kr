---
title: "대화 상자의 수명 주기 | Microsoft Docs"
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
  - "대화 상자, 수명 주기"
  - "대화 상자의 수명 주기"
  - "MFC 대화 상자, 수명 주기"
  - "모달 대화 상자, 수명 주기"
  - "모덜리스 대화 상자, 수명 주기"
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자의 수명 주기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

During the life cycle of a dialog box, the user invokes the dialog box, typically inside a command handler that creates and initializes the dialog object, the user interacts with the dialog box, and the dialog box closes.  
  
 For modal dialog boxes, your handler gathers any data the user entered once the dialog box closes.  Since the dialog object exists after its dialog window has closed, you can simply use the member variables of your dialog class to extract the data.  
  
 For modeless dialog boxes, you may often extract data from the dialog object while the dialog box is still visible.  At some point, the dialog object is destroyed; when this happens depends on your code.  
  
## 추가 정보  
  
-   [Creating and displaying dialog boxes](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Creating modal dialog boxes](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Creating modeless dialog boxes](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Using a dialog template in memory](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Setting the dialog box's background color](../mfc/setting-the-dialog-box’s-background-color.md)  
  
-   [Initializing the dialog box](../mfc/initializing-the-dialog-box.md)  
  
-   [Handling Windows messages in your dialog box](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Retrieving data from the dialog object](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [Closing the dialog box](../mfc/closing-the-dialog-box.md)  
  
-   [Destroying the dialog box](../mfc/destroying-the-dialog-box.md)  
  
-   [Dialog data exchange \(DDX\) and validation \(DDV\)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Property sheet dialog boxes](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)