---
title: "인쇄 | Microsoft Docs"
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
  - "문서, 인쇄"
  - "인쇄[MFC]"
  - "인쇄[MFC], 프레임워크에서"
  - "뷰 클래스, 인쇄 작업"
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 인쇄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows implements device\-independent display.  In MFC, this means that the same drawing calls, in the `OnDraw` member function of your view class, are responsible for drawing on the display and on other devices, such as printers.  For print preview, the target device is a simulated printer output to the display.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Your Role in Printing vs. the Framework's Role  
 Your view class has the following responsibilities:  
  
-   Inform the framework how many pages are in the document.  
  
-   When asked to print a specified page, draw that portion of the document.  
  
-   Allocate and deallocate any fonts or other graphics device interface \(GDI\) resources needed for printing.  
  
-   If necessary, send any escape codes needed to change the printer mode before printing a given page, for example, to change the printing orientation on a per\-page basis.  
  
 The framework's responsibilities are as follows:  
  
-   Display the **Print** dialog box.  
  
-   Create a [CDC](../mfc/reference/cdc-class.md) object for the printer.  
  
-   Call the [StartDoc](../Topic/CDC::StartDoc.md) and [EndDoc](../Topic/CDC::EndDoc.md) member functions of the `CDC` object.  
  
-   Repeatedly call the [StartPage](../Topic/CDC::StartPage.md) member function of the `CDC` object, inform the view class which page should be printed, and call the [EndPage](../Topic/CDC::EndPage.md) member function of the `CDC` object.  
  
-   Call overridable functions in the view at the appropriate times.  
  
 The following articles discuss how the framework supports printing and print preview:  
  
### 추가 정보  
  
-   [How default printing is done](../mfc/how-default-printing-is-done.md)  
  
-   [Multipage documents](../mfc/multipage-documents.md)  
  
-   [Headers and footers](../mfc/headers-and-footers.md)  
  
-   [Allocating GDI resources for printing](../mfc/allocating-gdi-resources.md)  
  
-   [Print preview](../mfc/print-preview-architecture.md)  
  
## 참고 항목  
 [인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)