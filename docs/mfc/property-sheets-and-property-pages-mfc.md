---
title: "속성 시트 및 속성 페이지(MFC) | Microsoft Docs"
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
  - "CPropertyPage 클래스, 속성 시트 및 페이지"
  - "CPropertySheet 클래스, 속성 시트 및 페이지"
  - "MFC 대화 상자, 탭"
  - "속성 페이지, 속성 시트"
  - "속성 시트, 속성 페이지"
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 속성 시트 및 속성 페이지(MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An MFC [dialog box](../mfc/dialog-boxes.md) can take on a "tab dialog" look by incorporating property sheets and property pages.  Called a "property sheet" in MFC, this kind of dialog box, similar to many dialog boxes in Microsoft Word, Excel, and Visual C\+\+, appears to contain a stack of tabbed sheets, much like a stack of file folders seen from front to back, or a group of cascaded windows.  Controls on the front tab are visible; only the labeled tab is visible on the rear tabs.  Property sheets are particularly useful for managing large numbers of properties or settings that fall fairly neatly into several groups.  Typically, one property sheet can simplify a user interface by replacing several separate dialog boxes.  
  
 As of MFC version 4.0, property sheets and property pages are implemented using the common controls that come with Windows 95 and Windows NT version 3.51 and later.  
  
 Property sheets are implemented with classes [CPropertySheet](../mfc/reference/cpropertysheet-class.md) and [CPropertyPage](../mfc/reference/cpropertypage-class.md) \(described in the *MFC Reference*\).  `CPropertySheet` defines the overall dialog box, which can contain multiple "pages" based on `CPropertyPage`.  
  
 For information on creating and working with property sheets, see the topic [Property Sheets](../mfc/property-sheets-mfc.md).  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [MFC의 속성 시트 및 속성 페이지](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [데이터 교환](../mfc/exchanging-data.md)   
 [모덜리스 속성 시트 만들기](../mfc/creating-a-modeless-property-sheet.md)   
 [적용 단추 처리](../mfc/handling-the-apply-button.md)