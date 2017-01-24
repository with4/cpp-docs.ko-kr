---
title: "이미지 목록 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CListCtrl 클래스, 이미지 목록 만들기"
  - "이미지 목록[C++], CListCtrl 만들기"
  - "목록[C++], 이미지"
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이미지 목록 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Creating image lists is the same whether you use [CListView](../mfc/reference/clistview-class.md) or [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  You only need image lists if your list control includes the `LVS_ICON` style.  
  
 Use class `CImageList` to create one or more image lists \(for full\-size icons, small icons, and states\).  See [CImageList](../mfc/reference/cimagelist-class.md), and see [List View Image Lists](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Call [CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md) for each image list; pass a pointer to the appropriate `CImageList` object.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)