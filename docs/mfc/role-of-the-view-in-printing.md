---
title: "인쇄에서 뷰의 역할 | Microsoft Docs"
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
  - "CView 클래스, 인쇄에서의 역할"
  - "OnDraw 메서드, 및 인쇄"
  - "인쇄[MFC], OnDraw 메서드"
  - "인쇄[MFC], 뷰"
  - "뷰 인쇄"
  - "뷰, 인쇄"
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 인쇄에서 뷰의 역할
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Your view also plays two important roles in printing its associated document.  
  
 The view:  
  
-   Uses the same [OnDraw](../Topic/CView::OnDraw.md) code to draw on the printer as to draw on the screen.  
  
-   Manages dividing the document into pages for printing.  
  
 For more information about printing and about the view's role in printing, see [Printing and Print Preview](../mfc/printing-and-print-preview.md).  
  
## 참고 항목  
 [뷰 사용](../mfc/using-views.md)