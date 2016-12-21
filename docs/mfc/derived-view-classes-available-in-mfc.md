---
title: "MFC에서 사용할 수 있는 파생된 뷰 클래스 | Microsoft Docs"
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
  - "클래스[C++], 파생"
  - "CView 클래스, 파생된 클래스"
  - "파생 클래스, 뷰 클래스"
  - "뷰 클래스, 파생"
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC에서 사용할 수 있는 파생된 뷰 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows MFC's view classes and their relationships to one another.  The capabilities of your view class depend on the MFC view class from which it derives.  
  
### View Classes  
  
|클래스|설명|  
|---------|--------|  
|[CView](../mfc/reference/cview-class.md)|Base class of all views.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Base class of `CTreeView`, `CListView`, `CEditView`, and `CRichEditView`.  These classes let you use document\/view architecture with the indicated Windows common controls.|  
|[CEditView](../mfc/reference/ceditview-class.md)|A simple view based on the Windows edit box control.  Allows entering and editing text and can be used as the basis for a simple text editor application.  `CRichEditView`을 참조하십시오.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|A view containing a [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) object.  This class is analogous to `CEditView`, but unlike `CEditView`, `CRichEditView` handles formatted text.|  
|[CListView](../mfc/reference/clistview-class.md)|A view containing a [CListCtrl](../mfc/reference/clistctrl-class.md) object.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|A view containing a [CTreeCtrl](../mfc/reference/ctreectrl-class.md) object, for views that resemble the Solution Explorer window in Visual C\+\+.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Base class of `CFormView`, `CRecordView`, and `CDaoRecordView`.  Implements scrolling the view's contents.|  
|[CFormView](../mfc/reference/cformview-class.md)|A form view, a view that contains controls.  A forms\-based application provides one or more such form interfaces.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|A Web browser view with which the application's user can browse sites on the World Wide Web, as well as folders in the local file system and on a network.  The Web browser view can also work as an Active document container.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|A form view that displays ODBC database records in controls.  If you select ODBC support in your project, the view's base class is `CRecordView`.  The view is connected to a `CRowset` object.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|A form view that displays DAO database records in controls.  If you select DAO support in your project, the view's base class is `CDaoRecordView`.  The view is connected to a `CDaoRecordset` object.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|A form view that displays OLE DB records in controls.  If you select OLE DB support in your project, the view's base class is `COleDBRecordView`.  The view is connected to a `CRowset` object.|  
  
> [!NOTE]
>  As of MFC version 4.0, `CEditView` is derived from `CCtrlView`.  
  
 To use these classes in your application, derive the application's view classes from them.  For related information, see [Scrolling and Scaling Views](../mfc/scrolling-and-scaling-views.md).  For more information on the database classes, see [Overview: Database Programming](../data/data-access-programming-mfc-atl.md).  
  
## 참고 항목  
 [뷰 사용](../mfc/using-views.md)