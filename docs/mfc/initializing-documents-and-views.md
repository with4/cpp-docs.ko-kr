---
title: "문서 및 뷰 초기화 | Microsoft Docs"
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
  - "문서, 초기화"
  - "문서 초기화"
  - "개체 초기화, 문서 개체"
  - "뷰 초기화"
  - "뷰, 초기화"
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 문서 및 뷰 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Documents are created in two different ways, so your document class must support both ways.  First, the user can create a new, empty document with the File New command.  In that case, initialize the document in your override of the [OnNewDocument](../Topic/CDocument::OnNewDocument.md) member function of class [CDocument](../mfc/reference/cdocument-class.md).  Second, the user can use the Open command on the File menu to create a new document whose contents are read from a file.  In that case, initialize the document in your override of the [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) member function of class **CDocument**.  If both initializations are the same, you can call a common member function from both overrides, or `OnOpenDocument` can call `OnNewDocument` to initialize a clean document and then finish the open operation.  
  
 Views are created after their documents are created.  The best time to initialize a view is after the framework has finished creating the document, frame window, and view.  You can initialize your view by overriding the [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) member function of [CView](../mfc/reference/cview-class.md).  If you need to reinitialize or adjust anything each time the document changes, you can override [OnUpdate](../Topic/CView::OnUpdate.md).  
  
## 참고 항목  
 [문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)