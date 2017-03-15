---
title: "인쇄 및 인쇄 미리 보기 | Microsoft Docs"
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
  - "인쇄 미리 보기"
  - "인쇄 미리 보기"
  - "인쇄[C++]"
  - "인쇄[C++], 인쇄 미리 보기"
  - "인쇄[MFC]"
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 인쇄 및 인쇄 미리 보기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC supports printing and print preview for your program's documents via class [CView](../mfc/reference/cview-class.md).  For basic printing and print preview, simply override your view class's [OnDraw](../Topic/CView::OnDraw.md) member function, which you must do anyway.  That function can draw to the view on the screen, to a printer device context for an actual printer, or to a device context that simulates your printer on the screen.  
  
 You can also add code to manage multipage document printing and preview, to paginate your printed documents, and to add headers and footers to them.  
  
 This family of articles explains how printing is implemented in the Microsoft Foundation Class Library \(MFC\) and how to take advantage of the printing architecture already built into the framework.  The articles also explain how MFC supports easy implementation of print preview functionality and how you can use and modify that functionality.  
  
## 추가 정보  
  
-   [인쇄](../mfc/printing.md)  
  
-   [Print preview architecture](../mfc/print-preview-architecture.md)  
  
-   [샘플](../top/visual-cpp-samples.md)  
  
## 참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)