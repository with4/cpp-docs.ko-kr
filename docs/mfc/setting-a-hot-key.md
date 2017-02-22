---
title: "바로 가기 키 설정 | Microsoft Docs"
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
  - "선택키[C++], 바로 가기 키"
  - "CHotKeyCtrl 클래스, 바로 가기 키 설정"
  - "바로 가기 키[C++], 바로 가기 키"
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 바로 가기 키 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Your application can use the information provided by a hot key \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) control in one of two ways:  
  
-   Set up a global hot key for activating a nonchild window by sending a [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) message to the window to be activated.  
  
-   Set up a thread\-specific hot key by calling the Windows function [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## 참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)