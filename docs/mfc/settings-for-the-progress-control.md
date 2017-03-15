---
title: "진행률 컨트롤에 대한 설정 | Microsoft Docs"
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
  - "CProgressCtrl 클래스, 설정"
  - "Progress 컨트롤[C++], 설정"
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 진행률 컨트롤에 대한 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The basic settings for the progress control \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) are the range and current position.  The range represents the entire duration of the operation.  The current position represents the progress that your application has made toward completing the operation.  Any changes to the range or position cause the progress control to redraw itself.  
  
 By default, the range is set to 0 – 100, and the initial position is set to 0.  To retrieve the current range settings for the progress control, use the [GetRange](../Topic/CProgressCtrl::GetRange.md) member function.  To change the range, use the [SetRange](../Topic/CProgressCtrl::SetRange.md) member function.  
  
 To set the position, use [SetPos](../Topic/CProgressCtrl::SetPos.md).  To retrieve the current position without specifying a new value, use [GetPos](../Topic/CProgressCtrl::GetPos.md).  For example, you might want to simply query on the status of the current operation.  
  
 To step the current position of the progress control, use [StepIt](../Topic/CProgressCtrl::StepIt.md).  To set the amount of each step, use [SetStep](../Topic/CProgressCtrl::SetStep.md)  
  
## 참고 항목  
 [CProgressCtrl 사용](../mfc/using-cprogressctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)