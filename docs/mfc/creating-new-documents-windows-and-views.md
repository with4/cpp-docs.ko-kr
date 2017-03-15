---
title: "새 문서, 창 및 뷰 만들기 | Microsoft Docs"
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
  - "자식 창, MDI 만들기"
  - "MFC 기본 개체 사용자 지정"
  - "문서 개체, 만들기"
  - "프레임 창[C++], 만들기"
  - "뷰 초기화"
  - "MDI[C++], 창 만들기"
  - "MDI[C++], 프레임 창"
  - "MFC[C++], 문서"
  - "MFC[C++], 프레임 창"
  - "MFC[C++], 뷰"
  - "MFC 기본 개체"
  - "MFC 기본 개체, 사용자 지정"
  - "개체[C++], 문서 개체 만들기"
  - "재정의, 기본 뷰 동작"
  - "뷰 개체"
  - "뷰 개체, 만들기"
  - "뷰[C++], 초기화"
  - "뷰[C++], 기본 동작 재정의"
  - "창 개체[C++], 만들기"
  - "창[C++], 만들기"
  - "창[C++], MDI"
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 새 문서, 창 및 뷰 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following figures give an overview of the creation process for documents, views, and frame windows.  Other articles that focus on the participating objects provide further details.  
  
 Upon completion of this process, the cooperating objects exist and store pointers to each other.  The following figures show the sequence in which objects are created.  You can follow the sequence from figure to figure.  
  
 ![문서 만들기 시퀀스](../mfc/media/vc387l1.png "vc387L1")  
문서를 만드는 순서  
  
 ![프레임 창 만들기 시퀀스](../mfc/media/vc387l2.png "vc387L2")  
프레임 창을 만드는 순서  
  
 ![뷰 만들기 시퀀스](../mfc/media/vc387l3.png "vc387L3")  
뷰를 만드는 순서  
  
 For information about how the framework initializes the new document, view, and frame\-window objects, see classes [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), and [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) in the MFC Library Reference.  Also see [Technical Note 22](../mfc/tn022-standard-commands-implementation.md), which explains the creation and initialization processes further under its discussion of the framework's standard commands for the `New` and **Open** items on the **File** menu.  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Initializing Your Own Additions to These Classes  
 The preceding figures also suggest the points at which you can override member functions to initialize your application's objects.  An override of `OnInitialUpdate` in your view class is the best place to initialize the view.  The `OnInitialUpdate` call occurs immediately after the frame window is created and the view within the frame window is attached to its document.  For example, if your view is a scroll view \(derived from `CScrollView` rather than `CView`\), you should set the view size based on the document size in your `OnInitialUpdate` override. \(This process is described in the description of class [CScrollView](../mfc/reference/cscrollview-class.md).\) You can override the **CDocument** member functions `OnNewDocument` and `OnOpenDocument` to provide application\-specific initialization of the document.  Typically, you must override both since a document can be created in two ways.  
  
 In most cases, your override should call the base class version.  For more information, see the named member functions of classes [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), and [CWinApp](../mfc/reference/cwinapp-class.md) in the MFC Library Reference.  
  
## 참고 항목  
 [문서 템플릿 및 문서\/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서 템플릿 만들기](../mfc/document-template-creation.md)   
 [문서\/뷰 만들기](../mfc/document-view-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)