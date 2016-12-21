---
title: "문서 및 뷰 초기화 및 정리 | Microsoft Docs"
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
  - "문서 개체, 수명 주기"
  - "문서, 정리"
  - "문서, 초기화"
  - "문서 초기화"
  - "개체 초기화, 문서 개체"
  - "뷰 초기화"
  - "뷰, 정리"
  - "뷰, 초기화"
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 및 뷰 초기화 및 정리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Use the following guidelines for initializing and cleaning up after your documents and views:  
  
-   The MFC framework initializes documents and views; you initialize any data you add to them.  
  
-   The framework cleans up as documents and views close; you must deallocate any memory that you allocated on the heap from within the member functions of those documents and views.  
  
> [!NOTE]
>  Recall that initialization for the whole application is best done in your override of the [InitInstance](../Topic/CWinApp::InitInstance.md) member function of class `CWinApp`, and cleanup for the whole application is best done in your override of the `CWinApp` member function [ExitInstance](../Topic/CWinApp::ExitInstance.md).  
  
 The life cycle of a document \(and its frame window and view or views\) in an MDI application is as follows:  
  
1.  During dynamic creation, the document constructor is called.  
  
2.  For each new document, the document's [OnNewDocument](../Topic/CDocument::OnNewDocument.md) or [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) is called.  
  
3.  The user interacts with the document throughout its lifetime.  Typically this happens as the user works on document data through the view, selecting and editing the data.  The view passes changes on to the document for storage and updating other views.  During this time both the document and the view might handle commands.  
  
4.  The framework calls [DeleteContents](../Topic/CDocument::DeleteContents.md) to delete data specific to a document.  
  
5.  The document's destructor is called.  
  
 In an SDI application, step 1 is performed once, when the document is first created.  Then steps 2 through 4 are performed repeatedly each time a new document is opened.  The new document reuses the existing document object.  Finally, step 5 is performed when the application ends.  
  
## 추가 정보  
  
-   [Initializing Documents and Views](../mfc/initializing-documents-and-views.md)  
  
-   [Cleaning Up Documents and Views](../mfc/cleaning-up-documents-and-views.md)  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)