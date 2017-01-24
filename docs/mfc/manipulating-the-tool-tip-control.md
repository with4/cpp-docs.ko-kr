---
title: "도구 설명 컨트롤 조작 | Microsoft Docs"
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
  - "CToolTipCtrl 클래스, 도구 설명 특성 조작"
  - "도구 설명[C++], 특성"
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 설명 컨트롤 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Class `CToolTipCtrl` provides a group of member functions that control the various attributes of the `CToolTipCtrl` object and the tool tip window.  
  
 The initial, pop\-up, and reshow durations for the tool tip windows can be set and retrieved with calls to [GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md) and [SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md).  
  
 Change the appearance of the tool tip windows with the following functions:  
  
-   [GetMargin](../Topic/CToolTipCtrl::GetMargin.md) and [SetMargin](../Topic/CToolTipCtrl::SetMargin.md) Retrieves and sets the width between the tool tip border and the tool tip text.  
  
-   [GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md) and [SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md) Retrieves and sets the maximum width of the tool tip window.  
  
-   [GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md) and [SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md) Retrieves and sets the background color of the tool tip window.  
  
-   [GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md) and [SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md) Retrieves and sets the text color of the tool tip window.  
  
 In order for the tool tip control to be notified of important messages, such as **WM\_LBUTTONXXX** messages, you must relay the messages to your tool tip control.  The best method for this relay is to make a call to [CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md), in the `PreTranslateMessage` function of the owner window.  The following example illustrates one possible method \(assuming the tool tip control is called `m_ToolTip`\):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/CPP/manipulating-the-tool-tip-control_1.cpp)]  
  
 To immediately remove a tool tip window, call the [Pop](../Topic/CToolTipCtrl::Pop.md) member function.  
  
## 참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)