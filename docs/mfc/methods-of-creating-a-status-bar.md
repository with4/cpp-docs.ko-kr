---
title: "상태 표시줄을 만드는 방법 | Microsoft Docs"
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
  - "CStatusBar 클래스, CStatusBarCtrl과 비교"
  - "CStatusBarCtrl 클래스, 만들기"
  - "CStatusBarCtrl 클래스, CStatusBar와 비교"
  - "메서드[MFC]"
  - "메서드[MFC], 상태 표시줄 만들기"
  - "상태 표시줄, 만들기"
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 상태 표시줄을 만드는 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC provides two classes to create status bars: [CStatusBar](../mfc/reference/cstatusbar-class.md) and [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) \(which wraps the Windows common control API\).  `CStatusBar` provides all of the functionality of the status bar common control, it automatically interacts with menus and toolbars, and it handles many of the required common control settings and structures for you; however, your resulting executable usually will be larger than that created by using `CStatusBarCtrl`.  
  
 `CStatusBarCtrl` usually results in a smaller executable, and you may prefer to use `CStatusBarCtrl` if you do not intend to integrate the status bar into the MFC architecture.  If you plan to use `CStatusBarCtrl` and integrate the status bar into the MFC architecture, you must take additional care to communicate status bar control manipulations to MFC.  This communication is not difficult; however, it is additional work that is unneeded when you use `CStatusBar`.  
  
 Visual C\+\+ provides two ways to take advantage of the status bar common control.  
  
-   Create the status bar using `CStatusBar`, and then call [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md) to get access to the `CStatusBarCtrl` member functions.  
  
-   Create the status bar using [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)'s constructor.  
  
 Either method will give you access to the member functions of the status bar control.  When you call `CStatusBar::GetStatusBarCtrl`, it returns a reference to a `CStatusBarCtrl` object so you can use either set of member functions.  See [CStatusBar](../mfc/reference/cstatusbar-class.md) for information on constructing and creating a status bar using `CStatusBar`.  
  
## 참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)