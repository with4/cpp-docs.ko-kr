---
title: "문서 템플릿 만들기 | Microsoft Docs"
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
  - "생성자[C++], 문서 템플릿"
  - "문서 템플릿"
  - "문서 템플릿, 만들기"
  - "MFC, 문서 템플릿"
  - "템플릿, 문서 템플릿"
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: 9
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 템플릿 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When creating a new document in response to a `New` or **Open** command from the **File** menu, the document template also creates a new frame window through which to view the document.  
  
 The document\-template constructor specifies what types of documents, windows, and views the template will be able to create.  This is determined by the arguments you pass to the document\-template constructor.  The following code illustrates creation of a [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) for a sample application:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/CPP/document-template-creation_1.cpp)]  
  
 The pointer to a new `CMultiDocTemplate` object is used as an argument to [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md).  Arguments to the `CMultiDocTemplate` constructor include the resource ID associated with the document type's menus and accelerators, and three uses of the [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md) macro.  `RUNTIME_CLASS` returns the [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) object for the C\+\+ class named as its argument.  The three `CRuntimeClass` objects passed to the document\-template constructor supply the information needed to create new objects of the specified classes during the document creation process.  The example shows creation of a document template that creates `CScribDoc` objects with `CScribView` objects attached.  The views are framed by standard MDI child frame windows.  
  
## 참고 항목  
 [문서 템플릿 및 문서\/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서\/뷰 만들기](../mfc/document-view-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)