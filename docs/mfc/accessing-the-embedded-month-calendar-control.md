---
title: "포함된 MonthCalendar 컨트롤 액세스 | Microsoft Docs"
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
  - "CDateTimeCtrl 클래스, 포함 컨트롤 액세스"
  - "CMonthCalCtrl 클래스, 글꼴 변경"
  - "DateTimePicker 컨트롤[MFC]"
  - "DateTimePicker 컨트롤[MFC], MonthCalendar 액세스"
  - "MonthCalendar 컨트롤, 글꼴 변경"
  - "MonthCalendar 컨트롤, 날짜/시간 선택에 포함"
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 포함된 MonthCalendar 컨트롤 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The embedded month calendar control object can be accessed from the `CDateTimeCtrl` object with a call to the [GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md) member function.  
  
> [!NOTE]
>  The embedded month calendar control is used only when the date and time picker control does not have the **DTS\_UPDOWN** style set.  
  
 This is useful if you want to modify certain attributes before the embedded control is displayed.  To accomplish this, handle the **DTN\_DROPDOWN** notification, retrieve the month calendar control \(using [CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)\), and make your modifications.  Unfortunately, the month calendar control is not persistent.  
  
 In other words, when the user requests the display of the month calendar control, a new month calendar control is created \(before the **DTN\_DROPDOWN** notification\).  The control is destroyed \(after the **DTN\_CLOSEUP** notification\) when dismissed by the user.  This means that any attributes you modify, before the embedded control is displayed, are lost when the embedded control is dismissed.  
  
 The following example demonstrates this procedure, using a handler for the **DTN\_DROPDOWN** notification.  The code changes the background color of the month calendar control, with a call to [SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md), to gray.  The code is as follows:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 As stated previously, all modifications to properties of the month calendar control are lost, with two exceptions, when the embedded control is dismissed.  The first exception, the colors of the month calendar control, has already been discussed.  The second exception is the font used by the month calendar control.  You can modify the default font by making a call to [CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md), passing the handle of an existing font.  The following example \(where `m_dtPicker` is the date and time control object\) demonstrates one possible method:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 Once the font has been changed, with a call to `CDateTimeCtrl::SetMonthCalFont`, the new font is stored and used the next time a month calendar is to be displayed.  
  
## 참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)