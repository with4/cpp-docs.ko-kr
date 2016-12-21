---
title: "CProgressCtrl 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl 클래스, using"
  - "Progress 컨트롤[C++]"
  - "Progress 컨트롤[C++], CProgressCtrl"
  - "Progress 컨트롤[C++], using"
ms.assetid: 61473270-196b-41ab-bf2b-467f46673539
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CProgressCtrl 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You can use the progress control to indicate the progress of a lengthy operation.  It is a rectangle that is gradually filled with the system highlight color as the operation progresses.  
  
 The progress control is represented in MFC by class [CProgressCtrl](../mfc/reference/cprogressctrl-class.md).  
  
 When you initially create the progress control, you specify its size and position, parent window \(usually a dialog box\), and ID.  By using the `dwStyle` parameter, you can also specify various window styles for the control and styles for how it fills.  
  
## 추가 정보  
  
-   [Styles for the Progress Control](../mfc/styles-for-the-progress-control.md)  
  
-   [Settings for the Progress Control](../mfc/settings-for-the-progress-control.md)  
  
-   [Manipulating the Progress Control](../mfc/manipulating-the-progress-control.md)  
  
## 참고 항목  
 [컨트롤](../mfc/controls-mfc.md)