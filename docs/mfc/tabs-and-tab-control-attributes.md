---
title: "탭 및 탭 컨트롤 특성 | Microsoft Docs"
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
  - "특성[C++], 참조 항목"
  - "CTabCtrl 클래스, 탭 컨트롤 특성"
  - "tab 컨트롤, 특성"
  - "탭"
  - "탭, 특성"
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 탭 및 탭 컨트롤 특성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You have considerable control over the appearance and behavior of tabs that make up a tab control \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\).  Each tab can have a label, an icon, an item state, and an application\-defined 32\-bit value associated with it.  For each tab, you can display the icon, the label, or both.  
  
 In addition, each tab item can have three possible states: pressed, unpressed, or highlighted.  This state can only be set by modifying an existing tab item.  To modify an existing tab item, retrieve it with a call to [GetItem](../Topic/CTabCtrl::GetItem.md), modify the `TCITEM` structure \(specifically the **dwState** and **dwStateMask** data members\), and then return the modified `TCITEM` structure with a call to [SetItem](../Topic/CTabCtrl::SetItem.md).  If you need to clear the item states of all the tab items in a `CTabCtrl` object, make a call to [DeselectAll](../Topic/CTabCtrl::DeselectAll.md).  This function resets the state of all tab items or all items except the one currently selected.  
  
 The following code clears the state of all tab items and then modifies the state of the third item:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/CPP/tabs-and-tab-control-attributes_1.cpp)]  
  
 For more information about tab attributes, see [Tabs and Tab Attributes](http://msdn.microsoft.com/library/windows/desktop/bb760550) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  For more information about adding tabs to a tab control, see [Adding Tabs to a Tab Control](../mfc/adding-tabs-to-a-tab-control.md) later in this topic.  
  
## 참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)