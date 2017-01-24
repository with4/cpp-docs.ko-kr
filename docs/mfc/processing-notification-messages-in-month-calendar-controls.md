---
title: "MonthCalendar 컨트롤에서 알림 메시지 처리 | Microsoft Docs"
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
  - "CMonthCalCtrl 클래스, 일 상태"
  - "CMonthCalCtrl 클래스, 알림"
  - "MonthCalendar 컨트롤, 알림 메시지"
  - "알림, CMonthCalCtrl"
  - "알림, MonthCalendar 컨트롤"
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MonthCalendar 컨트롤에서 알림 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As users interact with the month calendar control \(selecting dates and\/or viewing a different month\), the control \(`CMonthCalCtrl`\) sends notification messages to its parent window, usually a view or dialog object.  Handle these messages if you want to do something in response.  For example, when the user selects a new month to view, you could provide a set of dates that should be emphasized.  
  
 Use the Properties window to add notification handlers to the parent class for those messages you want to implement.  
  
 The following list describes the various notifications sent by the month calendar control.  
  
-   **MCN\_GETDAYSTATE** Requests information about which days should be displayed in bold.  For information on handling this notification, see [Setting the Day State of a Month Calendar Control](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN\_SELCHANGE** Notifies the parent that the selected date or range of the date has changed.  
  
-   **MCN\_SELECT** Notifies the parent that an explicit date selection has been made.  
  
## 참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)