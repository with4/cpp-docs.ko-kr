---
title: "진행률 컨트롤 조작 | Microsoft Docs"
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
  - "progress 컨트롤 제어"
  - "CProgressCtrl 클래스, 조작"
  - "CProgressCtrl 클래스, using"
  - "CProgressCtrl 클래스, 작업"
  - "Progress 컨트롤[C++], 조작"
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 진행률 컨트롤 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

There are three ways to change the current position of a progress control \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\).  
  
-   The position can be changed by a preset increment amount.  
  
-   The position can be changed by an arbitrary amount.  
  
-   The position can be changed to a specific value.  
  
### To change the position by a preset amount  
  
1.  Use the [SetStep](../Topic/CProgressCtrl::SetStep.md) member function to set the increment amount.  By default, this value is 10.  This value is typically set as one of the initial settings for the control.  The step value can be negative.  
  
2.  Use the [StepIt](../Topic/CProgressCtrl::StepIt.md) member function to increment the position.  This causes the control to redraw itself.  
  
    > [!NOTE]
    >  `StepIt` will cause the position to wrap.  For example, given a range of 1 –100, a step of 20, and a position of 90, `StepIt` will set the position to 10.  
  
### To change the position by an arbitrary amount  
  
1.  Use the [OffsetPos](../Topic/CProgressCtrl::OffsetPos.md) member function to change the position.  `OffsetPos` will accept negative values.  
  
    > [!NOTE]
    >  `OffsetPos`, unlike `StepIt`, will not wrap the position.  The new position is adjusted to remain within the range.  
  
### To change the position to a specific value  
  
1.  Use the [SetPos](../Topic/CProgressCtrl::SetPos.md) member function to set the position to a specific value.  If necessary, the new position is adjusted to be within the range.  
  
 Typically, the progress control is used solely for output.  To get the current position without specifying a new value, use [GetPos](../Topic/CProgressCtrl::GetPos.md).  
  
## 참고 항목  
 [CProgressCtrl 사용](../mfc/using-cprogressctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)