---
title: "머리글 및 바닥글 | Microsoft Docs"
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
  - "바닥글, 인쇄"
  - "머리글, 인쇄"
  - "페이지 바닥글"
  - "페이지 바닥글, 인쇄"
  - "페이지 머리글"
  - "페이지 머리글, 인쇄"
  - "인쇄[MFC], 머리글 및 바닥글"
  - "인쇄[MFC], 다중 페이지 문서"
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 머리글 및 바닥글
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains how to add headers and footers to a printed document.  
  
 When you look at a document on the screen, the name of the document and your current location in the document are commonly displayed in a title bar and a status bar.  When looking at a printed copy of a document, it's useful to have the name and page number shown in a header or footer.  This is a common way in which even WYSIWYG programs differ in how they perform printing and screen display.  
  
 The [OnPrint](../Topic/CView::OnPrint.md) member function is the appropriate place to print headers or footers because it is called for each page, and because it is called only for printing, not for screen display.  You can define a separate function to print a header or footer, and pass it the printer device context from `OnPrint`.  You might need to adjust the window origin or extent before calling [OnDraw](../Topic/CView::OnDraw.md) to avoid having the body of the page overlap the header or footer.  You might also have to modify `OnDraw` because the amount of the document that fits on the page could be reduced.  
  
 One way to compensate for the area taken by the header or footer is to use the **m\_rectDraw** member of [CPrintInfo](../mfc/reference/cprintinfo-structure.md).  Each time a page is printed, this member is initialized with the usable area of the page.  If you print a header or footer before printing the body of the page, you can reduce the size of the rectangle stored in **m\_rectDraw** to account for the area taken by the header or footer.  Then `OnPrint` can refer to **m\_rectDraw** to find out how much area remains for printing the body of the page.  
  
 You cannot print a header, or anything else, from [OnPrepareDC](../Topic/CView::OnPrepareDC.md), because it is called before the `StartPage` member function of [CDC](../mfc/reference/cdc-class.md) has been called.  At that point, the printer device context is considered to be at a page boundary.  You can perform printing only from the `OnPrint` member function.  
  
## 추가 정보  
  
-   [Printing multipage documents](../mfc/multipage-documents.md)  
  
-   [Allocating GDI resources for printing](../mfc/allocating-gdi-resources.md)  
  
## 참고 항목  
 [인쇄](../mfc/printing.md)