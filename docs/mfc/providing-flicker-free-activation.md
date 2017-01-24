---
title: "깜빡임 없는 활성화 제공 | Microsoft Docs"
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
  - "활성화[C++], 깜빡임 없는"
  - "깜빡임, MFC ActiveX 컨트롤"
  - "MFC ActiveX 컨트롤[C++], 깜빡임 없는"
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 깜빡임 없는 활성화 제공
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If your control draws itself identically in the inactive and active states \(and does not use windowless activation\), you can eliminate the drawing operations and the accompanying visual flicker that normally occur when making the transition between the inactive and active states.  To do this, include the **noFlickerActivate** flag in the set of flags returned by [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/CPP/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-flicker-free-activation_3.cpp)]  
  
 The code to include this flag is automatically generated if you select the **Flicker\-Free activation** option on the [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page when creating your control with the MFC ActiveX Control Wizard.  
  
 If you are using windowless activation, this optimization has no effect.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)