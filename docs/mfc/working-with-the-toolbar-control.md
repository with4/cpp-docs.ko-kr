---
title: "ToolBar 컨트롤 사용 | Microsoft Docs"
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
  - "CToolBarCtrl 클래스, 도구 모음 액세스"
  - "GetToolBarCtrl 메서드"
  - "도구 모음 컨트롤[MFC], 액세스"
  - "도구 모음[C++], 공용 컨트롤 액세스"
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ToolBar 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains how you can access the [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) object underlying a [CToolBar](../mfc/reference/ctoolbar-class.md) for greater control over your toolbars.  This is an advanced topic.  
  
## 절차  
  
#### To access the toolbar common control underlying your CToolBar object  
  
1.  Call [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md).  
  
 `GetToolBarCtrl` returns a reference to a [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) object.  You can use the reference to call member functions of the toolbar control class.  
  
> [!CAUTION]
>  While calling `CToolBarCtrl` **Get** functions is safe, use caution if you call the **Set** functions.  This is an advanced topic.  Normally you shouldn't need to access the underlying toolbar control.  
  
### 추가 정보  
  
-   [Controls \(Windows common controls\)](../mfc/controls-mfc.md)  
  
-   [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)  
  
-   [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)  
  
-   [Dynamically resizing the toolbar](../mfc/docking-and-floating-toolbars.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [Flyby status bar updates](../mfc/toolbar-tool-tips.md)  
  
-   [Handling tool tip notifications](../mfc/handling-tool-tip-notifications.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
-   [Handling customization notifications](../mfc/handling-customization-notifications.md)  
  
-   [Multiple toolbars](../mfc/toolbar-fundamentals.md)  
  
-   [Using your old toolbars](../mfc/using-your-old-toolbars.md)  
  
-   [Control bars](../mfc/control-bars.md)  
  
 For general information about using Windows common controls, see [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## 참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)