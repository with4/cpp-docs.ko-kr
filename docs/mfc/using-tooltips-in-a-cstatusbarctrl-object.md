---
title: "CStatusBarCtrl 개체에서 도구 설명 사용 | Microsoft Docs"
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
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl 클래스, 도구 설명"
  - "상태 표시줄, 도구 설명"
  - "도구 설명[C++], 상태 표시줄에서 사용"
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBarCtrl 개체에서 도구 설명 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To enable tooltips for a status bar control, create the `CStatusBarCtrl` object with the **SBT\_TOOLTIPS** style.  
  
> [!NOTE]
>  If you are using a `CStatusBar` object to implement your status bar, use the `CStatusBar::CreateEx` function.  It allows you to specify additional styles for the embedded **CStatusBarCtrl** object.  
  
 Once the `CStatusBarCtrl` object has been successfully created, use [CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md) and [CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md) to set and retrieve the tip text for a specific pane.  
  
 Once the tool tip has been set, it is displayed only if the part has an icon and no text, or if all of the text cannot be displayed inside the part.  Tool tips are not supported in simple mode.  
  
## 참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)