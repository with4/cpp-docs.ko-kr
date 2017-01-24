---
title: "탭 컨트롤 사용 | Microsoft Docs"
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
  - "CTabCtrl 클래스, using"
  - "tab 컨트롤, using"
  - "tab 컨트롤, 작업"
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 탭 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The easiest way to use a tab control \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) is by adding it to a dialog template resource with the dialog editor.  You can also use a tab control by itself.  MFC calls **InitCommonControls** for you.  The key tasks are as follows:  
  
-   [Creating the tab control](../mfc/creating-the-tab-control.md)  
  
-   [Adding tabs to a tab control](../mfc/adding-tabs-to-a-tab-control.md)  
  
-   [Processing tab control notification messages](../mfc/processing-tab-control-notification-messages.md)  
  
 If the tab control object is embedded in a parent view or dialog class, the control is destroyed when the parent is destroyed.  
  
## 참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)