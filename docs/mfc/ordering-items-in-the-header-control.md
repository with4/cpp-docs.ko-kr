---
title: "헤더 컨트롤에서 항목 순서 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DS_DRAGDROP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DS_DRAGDROP 알림"
  - "GetOrderArray 메서드"
  - "헤더 컨트롤, 항목 정렬"
  - "OrderToIndex 메서드"
  - "시퀀스"
  - "시퀀스, 헤더 컨트롤 항목"
  - "SetOrderArray 메서드"
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 헤더 컨트롤에서 항목 순서 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Once you've [added items to a header control](../mfc/adding-items-to-the-header-control.md), you can manipulate or get information about their order with the following functions:  
  
-   [CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md) and [CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)  
  
     Retrieves and sets the left\-to\-right order of header items.  
  
-   [CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md).  
  
     Retrieves the index value for a specific header item.  
  
 In addition to the previous member functions, the `HDS_DRAGDROP` style allows the user to drag and drop header items within the header control.  For more information, see [Providing Drag\-and\-Drop Support for Header Items](../mfc/providing-drag-and-drop-support-for-header-items.md).  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)