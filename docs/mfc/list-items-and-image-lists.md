---
title: "목록 항목 및 이미지 목록 | Microsoft Docs"
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
  - "CImageList 클래스, 및 목록 항목"
  - "CListCtrl 클래스, 이미지 목록"
  - "이미지 목록[C++], 목록 항목"
  - "목록 항목, 이미지 목록"
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 목록 항목 및 이미지 목록
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An "item" in a list control \([CListCtrl](../mfc/reference/clistctrl-class.md)\) consists of an icon, a label, and possibly other information \(in "subitems"\).  
  
 The icons for list control items are contained in image lists.  One image list contains full\-sized icons used in icon view.  A second, optional, image list contains smaller versions of the same icons for use in other views of the control.  A third optional list contains "state" images, such as check boxes, for display in front of the small icons in certain views.  A fourth optional list contains images that are displayed in individual header items of the list control.  
  
> [!NOTE]
>  If a list view control is created with the `LVS_SHAREIMAGELISTS` style, you are responsible for destroying the image lists when they are no longer in use.  Specify this style if you assign the same image lists to multiple list view controls; otherwise, more than one control might try to destroy the same image list.  
  
 For more information about list items, see [List View Image Lists](http://msdn.microsoft.com/library/windows/desktop/bb774736) and [Items and Subitems](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Also see class [CImageList](../mfc/reference/cimagelist-class.md) in the *MFC Reference* and [Using CImageList](../mfc/using-cimagelist.md) in this family of articles.  
  
 To create a list control, you need to supply image lists to be used when you insert new items into the list.  The following example demonstrates this procedure, where `m_pImagelist` is a pointer of type `CImageList` and `m_listctrl` is a `CListCtrl` data member.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/CPP/list-items-and-image-lists_1.cpp)]  
  
 However, if you don't plan to display icons in your list view or list control, you don't need image lists.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)