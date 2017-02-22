---
title: "헤더 컨트롤에 항목 추가 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 항목 추가"
  - "컨트롤[MFC], 헤더"
  - "헤더 컨트롤, 항목 추가"
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 헤더 컨트롤에 항목 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

After creating your header control \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) in its parent window, add as many "header items" as you need: usually one per column.  
  
### To add a header item  
  
1.  Prepare an [HD\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure.  
  
2.  Call [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md), passing the structure.  
  
3.  Repeat steps 1 and 2 for additional items.  
  
 For more information, see [Adding an Item to a Header Control](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)