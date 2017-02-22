---
title: "CStatusBarCtrl 개체의 일부 초기화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl 클래스, 파트 선언"
  - "CStatusBarCtrl 클래스, 단순 모드"
  - "아이콘, 상태 표시줄에서 사용"
  - "단순 상태 표시줄"
  - "상태 표시줄, 파트 선언"
  - "상태 표시줄, 아이콘"
  - "상태 표시줄, 단순 모드"
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CStatusBarCtrl 개체의 일부 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By default, a status bar displays status information using separate panes.  These panes \(also referred to as parts\) can contain either a text string, an icon, or both.  
  
 Use [SetParts](../Topic/CStatusBarCtrl::SetParts.md) to define how many parts, and the length, the status bar will have.  After you have created the parts of the status bar, make calls to [SetText](../Topic/CStatusBarCtrl::SetText.md) and [SetIcon](../Topic/CStatusBarCtrl::SetIcon.md) to set the text or icon for a specific part of the status bar.  Once the part has been successfully set, the control is automatically redrawn.  
  
 The following example initializes an existing `CStatusBarCtrl` object \(`m_StatusBarCtrl`\) with four panes and then sets an icon \(IDI\_ICON1\) and some text in the second part.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/CPP/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 For more information on setting the mode of a `CStatusBarCtrl` object to simple, see [Setting the Mode of a CStatusBarCtrl Object](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## 참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)