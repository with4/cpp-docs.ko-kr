---
title: "도구 설명에 대한 TTN_NEEDTEXT 알림 처리 | Microsoft Docs"
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
  - "TTN_NEEDTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "알림, 도구 설명"
  - "도구 설명[C++], 알림"
  - "TTN_NEEDTEXT 메시지"
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 설명에 대한 TTN_NEEDTEXT 알림 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As part of [enabling tool tips](../mfc/enabling-tool-tips.md), you handle the **TTN\_NEEDTEXT** message by adding the following entry to your owner window's message map:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 The member function to be called when text is needed for this button.  
  
 Note that the ID of a tool tip is always 0.  
  
 Declare your handler function in the class definition as follows:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 where the italicized parameters are:  
  
 `id`  
 Identifier of the control that sent the notification.  사용되지 않습니다.  The control id is taken from the **NMHDR** structure.  
  
 `pNMHDR`  
 A pointer to the [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) structure.  This structure is also discussed further in [The TOOLTIPTEXT Structure](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 A pointer to result code you can set before you return.  **TTN\_NEEDTEXT** handlers can ignore the `pResult` parameter.  
  
 As an example of a form\-view notification handler:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Call `EnableToolTips` \(this fragment taken from `OnInitDialog`\):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/CPP/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## 참고 항목  
 [CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)