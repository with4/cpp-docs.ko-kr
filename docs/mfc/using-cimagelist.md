---
title: "CImageList 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList 클래스, using"
  - "이미지 목록 컨트롤"
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CImageList 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An image list, represented by class [CImageList](../mfc/reference/cimagelist-class.md), is a collection of same\-sized images, each of which can be referred to by its index.  Image lists are used to efficiently manage large sets of icons or bitmaps.  Image lists are not themselves controls since they are not windows; however, they are used with several different types of controls, including list controls \([CListCtrl](../mfc/reference/clistctrl-class.md)\), tree controls \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\), and tab controls \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\).  
  
 All images in an image list are contained in a single, wide bitmap in screen\-device format.  An image list may also include a monochrome bitmap that contains masks used to draw images transparently \(icon style\).  `CImageList` provides member functions that enable you to draw images, create and destroy image lists, add and remove images, replace images, merge images, and drag images.  
  
## 추가 정보  
  
-   [Types of Image Lists](../mfc/types-of-image-lists.md)  
  
-   [Using an Image List](../mfc/using-an-image-list.md)  
  
-   [Manipulating Image Lists](../mfc/manipulating-image-lists.md)  
  
-   [Drawing Images from an Image List](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Image Overlays in Image Lists](../mfc/image-overlays-in-image-lists.md)  
  
-   [Dragging Images from an Image List](../mfc/dragging-images-from-an-image-list.md)  
  
-   [Image Information in Image Lists](../mfc/image-information-in-image-lists.md)  
  
## 참고 항목  
 [컨트롤](../mfc/controls-mfc.md)