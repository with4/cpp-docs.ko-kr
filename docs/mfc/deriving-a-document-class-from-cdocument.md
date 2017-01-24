---
title: "CDocument에서 문서 클래스 파생시키기 | Microsoft Docs"
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
  - "CDocument 클래스, 파생"
  - "클래스[C++], CDocument에서 파생"
  - "파생 클래스, 자주 재정의되는 함수"
  - "문서 클래스, 자주 재정의되는 함수"
  - "문서 개체, 파생"
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocument에서 문서 클래스 파생시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Documents contain and manage your application's data.  To use the MFC Application Wizard\-supplied document class, you must do the following:  
  
-   Derive a class from **CDocument** for each type of document.  
  
-   Add member variables to store each document's data.  
  
-   Override **CDocument**'s `Serialize` member function in your document class.  `Serialize` writes and reads the document's data to and from disk.  
  
## Other Document Functions Often Overridden  
 You may also want to override other **CDocument** member functions.  In particular, you will often need to override [OnNewDocument](../Topic/CDocument::OnNewDocument.md) and [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) to initialize the document's data members and [DeleteContents](../Topic/CDocument::DeleteContents.md) to destroy dynamically allocated data.  For information about overridable members, see class [CDocument](../mfc/reference/cdocument-class.md) in the *MFC Reference*.  
  
## 참고 항목  
 [문서 사용](../mfc/using-documents.md)