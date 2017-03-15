---
title: "MonthCalendar 컨트롤의 일 상태 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MCN_GETDAYSTATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl 클래스, 일 상태 정보 설정"
  - "MCN_GETDAYSTATE 알림"
  - "MonthCalendar 컨트롤, 일 상태 정보"
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MonthCalendar 컨트롤의 일 상태 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

One of the attributes of a month calendar control is the ability to store information, referred to as the day state of the control, for each day of the month.  This information is used to emphasize certain dates for the month currently displayed.  
  
> [!NOTE]
>  The `CMonthCalCtrl` object must have the **MCS\_DAYSTATE** style to display day state information.  
  
 Day state information is expressed as a 32\-bit data type, **MONTHDAYSTATE**.  Each bit in a **MONTHDAYSTATE** bit field \(1 through 31\) represents the state of a day in a month.  If a bit is on, the corresponding day will be displayed in bold; otherwise it will be displayed with no emphasis.  
  
 There are two methods for setting the day state of the month calendar control: explicitly with a call to [CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md) or by handling the **MCN\_GETDAYSTATE** notification message.  
  
## Handling the MCN\_GETDAYSTATE Notification Message  
 The **MCN\_GETDAYSTATE** message is sent by the control to determine how the days within the visible months should be displayed.  
  
> [!NOTE]
>  Because the control caches the previous and following months, in respect to the visible month, you will receive this notification every time a new month is chosen.  
  
 To properly handle this message, you must determine how many months day state information is being requested for, initialize an array of **MONTHDAYSTATE** structures with the proper values, and initialize the related structure member with the new information.  The following procedure, detailing the necessary steps, assumes that you have a `CMonthCalCtrl` object called `m_monthcal` and an array of **MONTHDAYSTATE** objects, `mdState`.  
  
#### To handle the MCN\_GETDAYSTATE notification message  
  
1.  Using the Properties window, add a notification handler for the **MCN\_GETDAYSTATE** message to the `m_monthcal` object \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  
  
2.  In the body of the handler, add the following code:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/CPP/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     The example converts the `pNMHDR` pointer to the proper type, then determines how many months of information are being requested \(`pDayState->cDayState`\).  For each month, the current bitfield \(`pDayState->prgDayState[i]`\) is initialized to zero and then the needed dates are set \(in this case, the 15th of each month\).  
  
## 참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)