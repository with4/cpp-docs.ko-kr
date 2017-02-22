---
title: "슬라이더 알림 메시지 | Microsoft Docs"
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
  - "CSliderCtrl 클래스, 알림"
  - "메시지, 알림"
  - "알림, CSliderCtrl"
  - "슬라이더 컨트롤, 알림 메시지"
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 슬라이더 알림 메시지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A slider control notifies its parent window of user actions by sending the parent `WM_HSCROLL` or `WM_VSCROLL` messages, depending on the orientation of the slider control.  To handle these messages, add handlers for the `WM_HSCROLL` and `WM_VSCROLL` messages to the parent window.  The [OnHScroll](../Topic/CWnd::OnHScroll.md) and [OnVScroll](../Topic/CWnd::OnVScroll.md) member functions will be passed a notification code, the position of the slider, and a pointer to the [CSliderCtrl](../mfc/reference/csliderctrl-class.md) object.  Note that the pointer is of type **CScrollBar \*** even though it points to a `CSliderCtrl` object.  You may need to typecast this pointer if you need to manipulate the slider control.  
  
 Rather than using the scroll bar notification codes, slider controls send a different set of notification codes.  A slider control sends the **TB\_BOTTOM**, **TB\_LINEDOWN**, **TB\_LINEUP**, and **TB\_TOP** notification codes only when the user interacts with a slider control by using the keyboard.  The **TB\_THUMBPOSITION** and **TB\_THUMBTRACK** notification messages are only sent when the user is using the mouse.  The **TB\_ENDTRACK**, **TB\_PAGEDOWN**, and **TB\_PAGEUP** notification codes are sent in both cases.  
  
 The following table lists the slider control notification messages and the events \(virtual key codes or mouse events\) that cause the notifications to be sent. \(For a list of standard virtual key codes, see Winuser.h.\)  
  
|Notification message|Event causing notification to be sent|  
|--------------------------|-------------------------------------------|  
|**TB\_BOTTOM**|**VK\_END**|  
|**TB\_ENDTRACK**|`WM_KEYUP` \(the user released a key that sent a relevant virtual key code\)|  
|**TB\_LINEDOWN**|**VK\_RIGHT** or **VK\_DOWN**|  
|**TB\_LINEUP**|**VK\_LEFT** or **VK\_UP**|  
|**TB\_PAGEDOWN**|**VK\_NEXT** \(the user clicked the channel below or to the right of the slider\)|  
|**TB\_PAGEUP**|**VK\_PRIOR** \(the user clicked the channel above or to the left of the slider\)|  
|**TB\_THUMBPOSITION**|`WM_LBUTTONUP` following a **TB\_THUMBTRACK** notification message|  
|**TB\_THUMBTRACK**|Slider movement \(the user dragged the slider\)|  
|**TB\_TOP**|**VK\_HOME**|  
  
## 참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)