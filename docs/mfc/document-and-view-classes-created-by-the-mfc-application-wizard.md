---
title: "MFC 응용 프로그램 마법사에서 만든 문서 및 뷰 클래스 | Microsoft Docs"
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
  - "응용 프로그램 마법사[C++], 만든 문서/뷰 클래스"
  - "문서 클래스"
  - "문서 클래스, 응용 프로그램 마법사로 만들기"
  - "뷰 클래스, 응용 프로그램 마법사로 만들기"
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC 응용 프로그램 마법사에서 만든 문서 및 뷰 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The MFC Application Wizard gives you a head start on your program development by creating skeletal document and view classes for you.  You can then [map commands and messages to these classes](../mfc/reference/mapping-messages-to-functions.md) and use the Visual C\+\+ source code editor to write their member functions.  
  
 The document class created by the MFC Application Wizard is derived from class [CDocument](../mfc/reference/cdocument-class.md).  The view class is derived from [CView](../mfc/reference/cview-class.md).  The names that the Application Wizard gives these classes and the files that contain them are based on the project name you supply in the Application Wizard dialog box.  In the Application Wizard, you can use the Generated Classes page to alter the default names.  
  
 Some applications might need more than one document class, view class, or frame\-window class.  For more information, see [Multiple Document Types, Views, and Frame Windows](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)