---
title: "트리 컨트롤과 통신 | Microsoft Docs"
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
  - "통신, 트리 컨트롤"
  - "CTreeCtrl 클래스, 멤버 함수 호출"
  - "트리 컨트롤"
  - "트리 컨트롤, 통신"
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 트리 컨트롤과 통신
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You use different methods for calling member functions in a [CTreeCtrl](../mfc/reference/ctreectrl-class.md) object depending on how the object was created:  
  
-   If the tree control is in a dialog box, use a member variable of type `CTreeCtrl` that you create in the dialog box class.  
  
-   If the tree control is a child window, use the `CTreeCtrl` object \(or pointer\) you used to construct the object.  
  
-   If you're using a `CTreeView` object, use the function [CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md) to get a reference to the tree control.  You can initialize another reference with this value or assign the address of the reference to a `CTreeCtrl` pointer.  
  
## 참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)