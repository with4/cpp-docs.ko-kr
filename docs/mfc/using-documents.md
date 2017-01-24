---
title: "문서 사용 | Microsoft Docs"
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
  - "데이터[MFC], 문서"
  - "데이터[MFC], 읽기"
  - "문서/뷰 아키텍처[C++], 문서"
  - "문서[C++]"
  - "문서[C++], C++ 응용 프로그램"
  - "파일[C++]"
  - "파일[C++], 쓰기"
  - "인쇄[MFC], 문서"
  - "데이터 읽기[C++], 문서 및 뷰"
  - "뷰[C++], C++ 응용 프로그램"
  - "파일에 쓰기[C++]"
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Working together, documents and views:  
  
-   Contain, manage, and display your application\-specific [data](../mfc/managing-data-with-document-data-variables.md).  
  
-   Provide an interface consisting of [document data variables](../mfc/managing-data-with-document-data-variables.md) for manipulating the data.  
  
-   Participate in [writing and reading files](../mfc/serializing-data-to-and-from-files.md).  
  
-   Participate in [printing](../mfc/role-of-the-view-in-printing.md).  
  
-   [Handle](../mfc/handling-commands-in-the-document.md) most of your application's commands and messages.  
  
 The document is particularly involved in managing data.  Store your data, normally, in document class member variables.  The view uses these variables to access the data for display and update.  The document's default serialization mechanism manages reading and writing the data to and from files.  Documents can also handle commands \(but not Windows messages other than **WM\_COMMAND**\).  
  
## 추가 정보  
  
-   [Deriving a document class from CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Managing data with document data variables](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Serializing data to and from files](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Bypassing the serialization mechanism](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Handling commands in the document](../mfc/handling-commands-in-the-document.md)  
  
-   [The OnNewDocument member function](../Topic/CDocument::OnNewDocument.md)  
  
-   [The DeleteContents member function](../Topic/CDocument::DeleteContents.md)  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)