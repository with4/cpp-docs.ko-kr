---
title: "Rich Edit 컨트롤 관련 클래스 | Microsoft Docs"
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
  - "클래스[C++], rich edit 컨트롤과 관련"
  - "CRichEditCtrl 클래스, 관련 클래스"
  - "CRichEditCtrlItem 클래스 및 CRichEditCtrl"
  - "CRichEditDoc 클래스, Rich Edit 컨트롤"
  - "CRichEditView 클래스, 및 CRichEditCtrl"
  - "rich edit 컨트롤, 및 CRichEditDoc"
  - "rich edit 컨트롤, 및 CRichEditItem"
  - "rich edit 컨트롤, 및 CRichEditView"
  - "rich edit 컨트롤, 관련된 클래스"
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Rich Edit 컨트롤 관련 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The [CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), and [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) classes provide the functionality of the rich edit control \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) within the context of MFC's document\/view architecture.  `CRichEditView` maintains the text and formatting characteristic of text.  `CRichEditDoc` maintains the list of OLE client items that are in the view.  `CRichEditCntrItem` provides container\-side access to the OLE client item.  To modify the contents of a `CRichEditView`, use [CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md) to access the underlying rich edit control.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)