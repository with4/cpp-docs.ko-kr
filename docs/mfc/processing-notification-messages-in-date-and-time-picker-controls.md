---
title: "날짜 및 시간 선택 컨트롤의 알림 메시지 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTN_CLOSEUP"
  - "DTN_DATETIMECHANGE"
  - "DTN_DROPDOWN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl 클래스, 알림 처리"
  - "DateTimePicker 컨트롤[MFC]"
  - "DateTimePicker 컨트롤[MFC], 알림 처리"
  - "DTN_CLOSEUP 알림"
  - "DTN_DATETIMECHANGE 알림"
  - "DTN_DROPDOWN 알림"
  - "DTN_FORMAT 알림"
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 날짜 및 시간 선택 컨트롤의 알림 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As users interact with the date and time picker control, the control \(`CDateTimeCtrl`\) sends notification messages to its parent window, usually a view or dialog object.  Handle these messages if you want to do something in response.  For example, when the user opens the date and time picker to display the embedded month calendar control, the **DTN\_DROPDOWN** notification is sent.  
  
 Use the Properties window to add notification handlers to the parent class for those messages you want to implement.  
  
 The following list describes the various notifications sent by the date and time picker control.  
  
-   **DTN\_DROPDOWN** Notifies the parent that the embedded month calendar control is about to be displayed.  This notification is only sent when the **DTS\_UPDOWN** style has not been set.  For more information on this notification, see [Accessing the Embedded Month Calendar Control](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN\_CLOSEUP** Notifies the parent that the embedded month calendar control is about to be closed.  This notification is only sent when the **DTS\_UPDOWN** style has not been set.  
  
-   **DTN\_DATETIMECHANGE** Notifies the parent that a change has occurred in the control.  
  
-   **DTN\_FORMAT** Notifies the parent that text is needed to be displayed in a callback field.  For more information on this notification and callback fields, see [Using Callback Fields in a Date and Time Picker Control](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_FORMATQUERY** Requests the parent to supply the maximum allowable size of the string that will be displayed in a callback field.  Handling this notification allows the control to properly display output at all times, reducing flicker within the control's display.  For more information on this notification, see [Using Callback Fields in a Date and Time Picker Control](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_USERSTRING** Notifies the parent that the user has finished editing the contents of the date and time picker control.  This notification is only sent when the **DTS\_APPCANPARSE** style has been set.  
  
-   **DTN\_WMKEYDOWN** Notifies the parent when the user types in a callback field.  Handle this notification to emulate the same keyboard response supported for non\-callback fields in a date and time picker control.  For more information on this notification, see [Supporting Callback Fields in a DTP Control](http://msdn.microsoft.com/library/windows/desktop/bb761726) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)