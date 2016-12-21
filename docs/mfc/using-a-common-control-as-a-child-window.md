---
title: "공용 컨트롤을 자식 창으로 사용 | Microsoft Docs"
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
  - "자식 창, 공용 컨트롤"
  - "공용 컨트롤[C++], 자식 창"
  - "컨트롤[MFC], 자식 창으로 사용"
  - "창[C++], 공용 컨트롤"
  - "Windows 공용 컨트롤[C++], 자식 창"
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공용 컨트롤을 자식 창으로 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Any of the Windows common controls can be used as a child window of any other window.  The following procedure describes how to create a common control dynamically and then work with it.  
  
### To use a common control as a child window  
  
1.  Define the control in the related class or handler.  
  
2.  Use the control's override of the [CWnd::Create](../Topic/CWnd::Create.md) method to create the Windows control.  
  
3.  After the control has been created \(as early as the `OnCreate` handler if you subclass the control\), you can manipulate the control using its member functions.  See the descriptions of individual controls at [컨트롤](../mfc/controls-mfc.md) for details on methods.  
  
4.  When you are finished with the control, use [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) to destroy the control.  
  
## 참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)