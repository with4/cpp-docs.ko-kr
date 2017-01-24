---
title: "뷰 사용 | Microsoft Docs"
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
  - "CView 클래스, 뷰 아키텍처"
  - "그리기, 데이터"
  - "뷰 클래스의 사용자 및 역할 상호 작용"
  - "MFC, 뷰"
  - "데이터 그리기"
  - "데이터 렌더링"
  - "사용자 입력, 뷰 클래스를 통해 해석"
  - "뷰 클래스, 응용 프로그램 데이터 표시에서의 역할"
  - "뷰 클래스, 사용자 상호 작용 관리에서의 역할"
  - "뷰, using"
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 뷰 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The view's responsibilities are to display the document's data graphically to the user and to accept and interpret user input as operations on the document.  Your tasks in writing your view class are to:  
  
-   Write your view class's [OnDraw](../Topic/CView::OnDraw.md) member function, which renders the document's data.  
  
-   Connect appropriate Windows messages and user\-interface objects such as menu items to message\-handler member functions in the view class.  
  
-   Implement those handlers to interpret user input.  
  
 In addition, you may need to override other `CView` member functions in your derived view class.  In particular, you may want to override [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) to perform special initialization for the view and [OnUpdate](../Topic/CView::OnUpdate.md) to do any special processing needed just before the view redraws itself.  For multipage documents, you also must override [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) to initialize the Print dialog box with the number of pages to print and other information.  For more information on overriding `CView` member functions, see class [CView](../mfc/reference/cview-class.md) in the *MFC Reference*.  
  
## 추가 정보  
  
-   [Derived view classes available in MFC](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Drawing in a view](../mfc/drawing-in-a-view.md)  
  
-   [Interpreting user input through a view](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [The role of the view in printing](../mfc/role-of-the-view-in-printing.md)  
  
-   [Scrolling and scaling views](../mfc/scrolling-and-scaling-views.md)  
  
-   [Initializing and cleaning up documents and views](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)   
 [CFormView Class](../mfc/reference/cformview-class.md)   
 [레코드 뷰  \(MFC Data Access\)](../data/record-views-mfc-data-access.md)   
 [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)