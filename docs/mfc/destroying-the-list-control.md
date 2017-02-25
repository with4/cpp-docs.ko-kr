---
title: "목록 컨트롤 소멸시키기 | Microsoft Docs"
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
  - "CListCtrl 클래스, 컨트롤 제거"
  - "list 컨트롤, 소멸"
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 목록 컨트롤 소멸시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If you embed your [CListCtrl](../mfc/reference/clistctrl-class.md) object as a data member of a view or dialog class, it is destroyed when its owner is destroyed.  If you use a [CListView](../mfc/reference/clistview-class.md), the framework destroys the control when it destroys the view.  
  
 If you arrange for some of your list data to be stored in the application rather than the list control, you will need to arrange for its deallocation.  For more information, see [Callback Items and the Callback Mask](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 In addition, you are responsible for deallocating any image lists you created and associated with the list control object.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)