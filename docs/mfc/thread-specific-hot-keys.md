---
title: "스레드 관련 바로 가기 키 | Microsoft Docs"
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
  - "CHotKeyCtrl 클래스, 스레드 관련 바로 가기 키"
  - "바로 가기 키[C++], 바로 가기 키"
  - "스레딩[C++], CHotKeyCtrl의 바로 가기 키"
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 스레드 관련 바로 가기 키
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An application sets a thread\-specific hot key \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) by using the Windows **RegisterHotKey** function.  When the user presses a thread\-specific hot key, Windows posts a [WM\_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) message to the beginning of a particular thread's message queue.  The **WM\_HOTKEY** message contains the virtual key code, shift state, and user\-defined ID of the specific hot key that was pressed.  For a list of standard virtual key codes, see Winuser.h.  For more information on this method, see [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Note that the shift state flags used in the call to **RegisterHotKey** are not the same as those returned by the [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md) member function; you'll have to translate these flags before calling **RegisterHotKey**.  
  
## 참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)