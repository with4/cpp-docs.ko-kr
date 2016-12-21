---
title: "날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용 | Microsoft Docs"
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
  - "CDateTimeCtrl 클래스, 표시 스타일"
  - "DateTimePicker 컨트롤[MFC]"
  - "DateTimePicker 컨트롤[MFC], 표시 스타일"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By default, date and time picker controls provide three format types \(each format corresponding to a unique style\) for displaying the current date or time:  
  
-   **DTS\_LONGDATEFORMAT** Displays the date in long format, producing output like "Wednesday, January 3, 2000".  
  
-   **DTS\_SHORTDATEFORMAT** Displays the date in short format, producing output like "1\/3\/00".  
  
-   **DTS\_TIMEFORMAT** Displays the time in long format, producing output like "5:31:42 PM".  
  
 However, you can customize the appearance of the date or time by using a custom format string.  This custom string is made up of either existing format characters, nonformat characters, or a combination of both.  Once the custom string is built, make a call to [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md) passing in your custom string.  The date and time picker control will then display the current value using your custom format string.  
  
 The following example code \(where `m_dtPicker` is the `CDateTimeCtrl` object\) demonstrates one possible solution:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/CPP/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 In addition to custom format strings, date and time picker controls also support [callback fields](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## 참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)