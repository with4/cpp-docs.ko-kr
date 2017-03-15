---
title: "속성 시트에 컨트롤 추가 | Microsoft Docs"
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
  - "컨트롤[MFC], 속성 시트에 추가"
  - "속성 시트, 컨트롤 추가"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 속성 시트에 컨트롤 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By default, a property sheet allocates window area for the property pages, the tab index, and the OK, Cancel, and Apply buttons. \(A modeless property sheet does not have the OK, Cancel, and Apply buttons.\) You can add other controls to the property sheet.  For example, you can add a preview window to the right of the property page area to show the user what the current settings would look like if applied to an external object.  
  
 You can add controls to the property sheet dialog in the `OnCreate` handler.  Accommodating additional controls usually requires expanding the size of the property sheet dialog.  After calling the base class **CPropertySheet::OnCreate**, call [GetWindowRect](../Topic/CWnd::GetWindowRect.md) to get the width and height of the currently allocated property sheet window, expand the rectangle's dimensions, and call [MoveWindow](../Topic/CWnd::MoveWindow.md) to change the size of the property sheet window.  
  
## 참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)   
 [CPropertyPage Class](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Class](../mfc/reference/cpropertysheet-class.md)