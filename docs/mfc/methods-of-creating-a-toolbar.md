---
title: "도구 모음을 만드는 방법 | Microsoft Docs"
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
  - "CToolBar 클래스, 도구 모음 만들기"
  - "CToolBarCtrl 클래스, 및 CToolBar 클래스"
  - "CToolBarCtrl 클래스, 도구 모음 만들기"
  - "MFC 도구 모음"
  - "도구 모음 컨트롤[MFC]"
  - "도구 모음 컨트롤[MFC], 만들기"
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 도구 모음을 만드는 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC provides two classes to create toolbars: [CToolBar](../mfc/reference/ctoolbar-class.md) and [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) \(which wraps the Windows common control API\).  `CToolBar` provides all of the functionality of the toolbar common control, and it handles many of the required common control settings and structures for you; however, your resulting executable usually will be larger than that created by using `CToolBarCtrl`.  
  
 `CToolBarCtrl` usually results in a smaller executable, and you may prefer to use `CToolBarCtrl` if you do not intend to integrate the toolbar into the MFC architecture.  If you plan to use `CToolBarCtrl` and integrate the toolbar into the MFC architecture, you must take additional care to communicate toolbar control manipulations to MFC.  This communication is not difficult; however, it is additional work that is unneeded when you use `CToolBar`.  
  
 Visual C\+\+ provides two ways to take advantage of the toolbar common control.  
  
-   Create the toolbar using `CToolBar`, and then call [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md) to get access to the `CToolBarCtrl` member functions.  
  
-   Create the toolbar using [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)'s constructor.  
  
 Either method will give you access to the member functions of the toolbar control.  When you call `CToolBar::GetToolBarCtrl`, it returns a reference to a `CToolBarCtrl` object so you can use either set of member functions.  See [CToolBar](../mfc/reference/ctoolbar-class.md) for information on constructing and creating a toolbar using `CToolBar`.  
  
## 참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)