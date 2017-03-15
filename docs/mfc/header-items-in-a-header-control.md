---
title: "헤더 컨트롤의 헤더 항목 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 헤더 항목"
  - "컨트롤[MFC], 헤더"
  - "헤더 컨트롤, 헤더 항목"
  - "헤더 컨트롤의 헤더 항목"
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 헤더 컨트롤의 헤더 항목
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You have considerable control over the appearance and behavior of the header items that make up a header control \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\).  Each header item can have a string, a bitmapped image, an image from an associated image list, or an application\-defined 32\-bit value associated with it.  The string, bitmap, or image is displayed in the header item.  
  
 You can customize the appearance and contents of new items when they are created by making a call [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md) or by modifying an existing item, with a call to [CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md) and [CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md).  
  
## 추가 정보  
  
-   [Customizing the header item's appearance](../mfc/customizing-the-header-item-s-appearance.md)  
  
-   [Ordering items in the header control](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Providing drag\-and\-drop support for the header items](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Using image lists with header controls](../mfc/using-image-lists-with-header-controls.md)  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)