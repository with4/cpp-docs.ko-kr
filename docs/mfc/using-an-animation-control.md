---
title: "애니메이션 컨트롤 사용 | Microsoft Docs"
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
  - "애니메이션 컨트롤[C++]"
  - "CAnimateCtrl 클래스, 애니메이션 컨트롤"
  - "컨트롤[MFC], 애니메이션"
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 애니메이션 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typical usage of an animation control follows the pattern below:  
  
-   The control is created.  If the control is specified in a dialog box template, creation is automatic when the dialog box is created. \(You should have a [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) member in your dialog class that corresponds to the animation control.\) Alternatively, you can use the [Create](../Topic/CAnimateCtrl::Create.md) member function to create the control as a child window of any window.  
  
-   Load an AVI clip into the animation control by calling the [Open](../Topic/CAnimateCtrl::Open.md) member function.  If your animation control is in a dialog box, a good place to do this is in the dialog class's [OnInitDialog](../Topic/CDialog::OnInitDialog.md) function.  
  
-   Play the clip by calling the [Play](../Topic/CAnimateCtrl::Play.md) member function.  If your animation control is in a dialog box, a good place to do this is in the dialog class's **OnInitDialog** function.  Calling **Play** is not necessary if the animation control has the `ACS_AUTOPLAY` style set.  
  
-   If you want to display portions of the clip or play it frame by frame, use the `Seek` member function.  To stop a clip that is playing, use the `Stop` member function.  
  
-   If you are not going to destroy the control right away, remove the clip from memory by calling the **Close** member function.  
  
-   If the animation control is in a dialog box, it and the `CAnimateCtrl` object will be destroyed automatically.  If not, you need to ensure that both the control and the `CAnimateCtrl` object are properly destroyed.  Destroying the control automatically closes the AVI clip.  
  
## 참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)