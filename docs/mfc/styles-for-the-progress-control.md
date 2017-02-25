---
title: "진행률 컨트롤 스타일 | Microsoft Docs"
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
  - "CProgressCtrl 클래스, 스타일"
  - "PBS_SMOOTH 스타일"
  - "PBS_VERTICAL 스타일"
  - "Progress 컨트롤[C++], 스타일"
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 진행률 컨트롤 스타일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you initially create the progress control \([CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)\), use the `dwStyle` parameter to specify the desired window styles for your progress control.  The following list details the applicable window styles.  The control ignores any window style other than the ones listed here.  You should always create the control as a child window, usually of a dialog box parent.  
  
|Window style|효과|  
|------------------|--------|  
|`WS_BORDER`|Creates a border around the window.|  
|**WS\_CHILD**|Creates a child window \(should always be used for `CProgressCtrl`\).|  
|**WS\_CLIPCHILDREN**|Excludes the area occupied by child windows when you draw within the parent window.  부모 창을 만들 때 사용합니다.|  
|**WS\_CLIPSIBLINGS**|Clips child windows relative to each other.|  
|**WS\_DISABLED**|Creates a window that is initially disabled.|  
|**WS\_VISIBLE**|Creates a window that is initially visible.|  
|**WS\_TABSTOP**|Specifies that the control can receive focus when the user presses the TAB key to move to it.|  
  
 In addition, you can specify two styles that apply only to the progress control, `PBS_VERTICAL` and `PBS_SMOOTH`.  
  
 Use `PBS_VERTICAL` to orient the control vertically, rather than horizontally.  Use `PBS_SMOOTH` to fill the control completely, rather than displaying small delineated squares that fill the control incrementally.  
  
 Without `PBS_SMOOTH` style:  
  
 ![표준 진행률 막대 스타일](../mfc/media/vc4ruw1.png "vc4RUW1")  
  
 With `PBS_SMOOTH` and `PBS_VERTICAL` styles:  
  
 ![진행률 막대 스타일, 부드러운 세로줄](../mfc/media/vc4ruw2.png "vc4RUW2")  
  
 For more information, see [Window Styles](../mfc/reference/frame-window-styles-mfc.md) in the *MFC Reference*.  
  
## 참고 항목  
 [CProgressCtrl 사용](../mfc/using-cprogressctrl.md)