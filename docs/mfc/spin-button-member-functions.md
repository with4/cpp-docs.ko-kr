---
title: "스핀 단추 멤버 함수 | Microsoft Docs"
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
  - "CSpinButtonCtrl 클래스, 메서드"
  - "spin button 컨트롤, 메서드"
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 스핀 단추 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

There are several member functions available for the spin control \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\).  Use these functions to change the following attributes of the spin button.  
  
-   **Acceleration** You can adjust the rate at which the position changes when the user holds down the arrow button.  To work with acceleration, use the [SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md) and [GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md) member functions.  
  
-   **Base** You can change the base \(either 10 or 16\) used to display the position in the caption of the buddy window.  To work with the base, use the [GetBase](../Topic/CSpinButtonCtrl::GetBase.md) and [SetBase](../Topic/CSpinButtonCtrl::SetBase.md) member functions.  
  
-   **Buddy Window** You can dynamically set the buddy window.  To query or change which control is the buddy window, use the [GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md) and [SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md) member functions.  
  
-   **Position** You can query and change the position.  To work directly with position, use the [GetPos](../Topic/CSpinButtonCtrl::GetPos.md) and [SetPos](../Topic/CSpinButtonCtrl::SetPos.md) member functions.  Since the caption of the buddy control may have changed \(for example, in the case that the buddy is an edit control\), `GetPos` retrieves the current caption and adjusts the position accordingly.  
  
-   **Range** You can change the maximum and minimum positions for the spin button.  By default, the maximum is set to 0, and the minimum is set to 100.  Since the default maximum is less than the default minimum, the actions of the arrow buttons is counter\-intuitive.  Typically, you will set the range using the [SetRange](../Topic/CSpinButtonCtrl::SetRange.md) member function.  To query the range use [GetRange](../Topic/CSpinButtonCtrl::GetRange.md).  
  
## 참고 항목  
 [CSpinButtonCtrl 사용](../mfc/using-cspinbuttonctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)