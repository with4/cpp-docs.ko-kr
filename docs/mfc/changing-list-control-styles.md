---
title: "목록 컨트롤 스타일 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CListCtrl 클래스, 스타일 변경"
  - "CListCtrl 클래스, 스타일"
  - "스타일, CListCtrl"
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 목록 컨트롤 스타일 변경
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You can change the window style of a list control \([CListCtrl](../mfc/reference/clistctrl-class.md)\) at any time after you create it.  By changing the window style, you change the kind of view the control uses.  For example, to emulate the Explorer, you might supply menu items or toolbar buttons for switching the control between different views: icon view, list view, and so on.  
  
 For example, when the user selects your menu item, you could make a call to [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) to retrieve the current style of the control and then call [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) to reset the style.  For more information, see [Using List View Controls](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Available styles are listed in [Create](../Topic/CListCtrl::Create.md).  The styles `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, and `LVS_REPORT` designate the four list control views.  
  
## 확장 스타일  
 In addition to the standard styles for a list control, there is another set, referred to as extended styles.  These styles, discussed in [Extended List View Styles](http://msdn.microsoft.com/library/windows/desktop/bb774732) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], provide a variety of useful features that customize the behavior of your list control.  To implement the behavior of a certain style \(such as hover selection\), make a call to [CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md), passing the needed style.  The following example demonstrates the function call:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/CPP/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  For hover selection to work, you must also have either **LVS\_EX\_ONECLICKACTIVATE** or **LVS\_EX\_TWOCLICKACTIVATE** turned on.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)