---
title: "문서/뷰 만들기 | Microsoft Docs"
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
  - "문서/뷰 아키텍처, 문서/뷰 만들기"
  - "문서, 만들기"
  - "MFC, 문서"
  - "MFC, 뷰"
  - "개체 작성자"
  - "테이블[C++]"
  - "테이블[C++], 각 MFC 개체가 만드는 개체"
  - "뷰, 및 프레임 창"
  - "뷰, 만들기"
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 문서/뷰 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The framework supplies implementations of the `New` and **Open** commands \(among others\) on the **File** menu.  Creation of a new document and its associated view and frame window is a cooperative effort among the application object, a document template, the newly created document, and the newly created frame window.  The following table summarizes which objects create what.  
  
### Object Creators  
  
|Creator|Creates|  
|-------------|-------------|  
|Application 개체|Document template|  
|Document template|Document|  
|Document template|Frame window|  
|Frame window|보기|  
  
## 참고 항목  
 [문서 템플릿 및 문서\/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서 템플릿 만들기](../mfc/document-template-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)