---
title: "표시되었을 때 활성화 옵션 해제 | Microsoft Docs"
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
  - "MFC ActiveX 컨트롤[C++], 활성화 옵션"
  - "표시되었을 때 활성화 옵션"
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 표시되었을 때 활성화 옵션 해제
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤은 활성 및 비활성의 두 가지 기본 상태를 가집니다.  전통적으로, 이러한 상태는 컨트롤이 창을 가졌는지의 여부에 의해 구별됩니다.  활성 컨트롤은 창을 가지지만 비활성 컨트롤은 그렇지 않습니다.  창 없는 활성화의 도입에 의해, 이러한 구분은 더 이상 절대적이지 않습니다. 그러나 여전히 많은 컨트롤에 적용됩니다.  
  
 Compared with the rest of the initialization typically performed by an ActiveX control, the creation of a window is an extremely expensive operation.  Ideally, a control would defer creating its window until absolutely necessary.  
  
 Many controls do not need to be active the entire time they are visible in a container.  Often, a control can remain in the inactive state until the user performs an operation that requires it to become active \(for example, clicking with the mouse or pressing the TAB key\).  To cause a control to remain inactive until the container needs to activate it, remove the **OLEMISC\_ACTIVATEWHENVISIBLE** flag from the control's miscellaneous flags:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/CPP/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 The **OLEMISC\_ACTIVATEWHENVISIBLE** flag is automatically omitted if you turn off the **Activate When Visible** option in the [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page of the MFC ActiveX Control Wizard when you create your control.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)