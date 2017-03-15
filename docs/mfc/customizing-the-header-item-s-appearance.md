---
title: "헤더 항목의 모양 사용자 지정 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 항목 사용자 지정"
  - "HDS_ 스타일"
  - "헤더 컨트롤, 항목의 사용자 지정"
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 헤더 항목의 모양 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By setting the *dwStyle* parameter when you first create a header control \([CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)\), you can define the appearance and behavior of header items or of the header control itself.  
  
 Here is a sampling of the styles you can set, and their purpose:  
  
-   To make a header item look like a pushbutton, use the `HDS_BUTTONS` style.  
  
     Use this style if you want to carry out actions in response to mouse clicks on a header item, such as sorting data by a particular column, as is done in Microsoft Outlook.  
  
-   To give the header items a "hot tracking" appearance when the mouse cursor passes over them, use the `HDS_HOTTRACK` style.  
  
     Hot tracking displays a 3D outline as the pointer passes over an item in an otherwise flat bar.  
  
-   To indicate that the header control should be hidden, use the `HDS_HIDDEN` style.  
  
     The `HDS_HIDDEN` style indicates that the header control is intended to be used as a data container and not a visual control.  This style does not automatically hide the control but, instead, affects the behavior of `CHeaderCtrl::Layout`.  The value returned in the **cy** member of the `WINDOWPOS` structure will be zero indicating that the control should not be visible to the user.  
  
 For more information about these properties, see [Items](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  For information about adding items to a header control, see [Adding Items to the Header Control](../mfc/adding-items-to-the-header-control.md).  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)