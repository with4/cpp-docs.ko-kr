---
title: "문서/뷰 아키텍처에 대한 자세한 설명 | Microsoft Docs"
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
  - "문서/뷰 아키텍처"
  - "문서/뷰 아키텍처, 문서/뷰 아키텍처 정보"
  - "문서/뷰 아키텍처, 뷰에서 데이터 액세스"
  - "문서, 뷰에서 데이터 액세스"
  - "문서, 다중 뷰"
  - "문서, 뷰"
  - "입력, 뷰 클래스"
  - "다중 뷰, 문서에서 업데이트"
  - "뷰, 문서 데이터 액세스"
  - "뷰, 및 사용자 입력"
  - "뷰, 업데이트"
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서/뷰 아키텍처에 대한 자세한 설명
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Documents and views are paired in a typical MFC application.  Data is stored in the document, but the view has privileged access to the data.  The separation of document from view separates the storage and maintenance of data from its display.  
  
## Gaining Access to Document Data from the View  
 The view accesses its document's data either with the [GetDocument](../Topic/CView::GetDocument.md) function, which returns a pointer to the document, or by making the view class a C\+\+ `friend` of the document class.  The view then uses its access to the data to obtain the data when it is ready to draw or otherwise manipulate it.  
  
 For example, from the view's [OnDraw](../Topic/CView::OnDraw.md) member function, the view uses **GetDocument** to obtain a document pointer.  Then it uses that pointer to access a `CString` data member in the document.  The view passes the string to the `TextOut` function.  To see the code for this example, see [Drawing in a View](../mfc/drawing-in-a-view.md).  
  
## User Input to the View  
 The view might also interpret a mouse click within itself as either selection or editing of data.  Similarly it might interpret keystrokes as data entry or editing.  Suppose the user types a string in a view that manages text.  The view obtains a pointer to the document and uses the pointer to pass the new data to the document, which stores it in some data structure.  
  
## Updating Multiple Views of the Same Document  
 In an application with multiple views of the same document — such as a splitter window in a text editor — the view first passes the new data to the document.  Then it calls the document's [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) member function, which tells all views of the document to update themselves, reflecting the new data.  This synchronizes the views.  
  
### 추가 정보  
  
-   [Advantages of the document\/view architecture](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Alternatives to the document\/view architecture](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)