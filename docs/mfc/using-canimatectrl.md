---
title: "CAnimateCtrl 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "애니메이션 컨트롤[C++], CAnimateCtrl 클래스"
  - "CAnimateCtrl 클래스, CAnimateCtrl 클래스 정보"
  - "컨트롤[MFC], 애니메이션"
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CAnimateCtrl 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An animation control, represented by the class [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), is a window that displays a clip in Audio Video Interleaved \(AVI\) format — the standard Windows video\/audio format.  An AVI clip is a series of bitmap frames, like a movie.  
  
 Since your thread continues executing while the AVI clip is displayed, one common use for an animation control is to indicate system activity during a lengthy operation.  For example, the Windows Find dialog box displays a moving magnifying glass as the system searches for a file.  
  
 Animation controls can only play simple AVI clips, and they do not support sound. \(For a complete list of limitations, see [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).\) Since the capabilities of an animation control are severely limited and subject to change, you should use an alternative such as the MCIWnd control if you need a control to provide multimedia playback and\/or recording capabilities.  For more information about the MCIWnd control, see the multimedia documentation.  
  
## 추가 정보  
  
-   [Using an Animation Control](../mfc/using-an-animation-control.md)  
  
-   [Notifications Sent by Animation Controls](../mfc/notifications-sent-by-animation-controls.md)  
  
## 참고 항목  
 [컨트롤](../mfc/controls-mfc.md)