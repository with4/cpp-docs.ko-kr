---
title: "헤더 항목에 대한 끌어서 놓기 지원 제공 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 끌어서 놓기 지원"
  - "HDN_ 알림"
  - "HDS_DRAGDROP 스타일"
  - "헤더 컨트롤의 헤더 항목"
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 헤더 항목에 대한 끌어서 놓기 지원 제공
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To provide drag\-and\-drop support for header items, specify the `HDS_DRAGDROP` style.  Drag\-and\-drop support for header items gives the user the ability to reorder the header items of a header control.  The default behavior provides a semitransparent drag image of the header item being dragged and a visual indicator of the new position, if the header item is dropped.  
  
 As with common drag\-and\-drop functionality, you can extend the default drag\-and\-drop behavior by handling the **HDN\_BEGINDRAG** and **HDN\_ENDDRAG** notifications.  You can also customize the appearance of the drag image by overriding the [CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md) member function.  
  
> [!NOTE]
>  If you are providing drag\-and\-drop support for an embedded header control in a list control, see the Extended Style section in the [Changing List Control Styles](../mfc/changing-list-control-styles.md) topic.  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)