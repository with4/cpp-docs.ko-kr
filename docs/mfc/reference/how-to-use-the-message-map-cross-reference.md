---
title: "방법: 메시지 맵 상호 참조 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "창[C++], 메시지 맵"
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 메시지 맵 상호 참조 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In entries labeled \<memberFxn\>, write your own member function for a derived [CWnd](../../mfc/reference/cwnd-class.md) class.  Give your function any name you like.  Other functions, such as `OnActivate`, are member functions of class `CWnd`.  If called, they pass the message to the `DefWindowProc` Windows function.  To process Windows notification messages, override the corresponding `CWnd` function in your derived class.  Your function should call the overridden function in your base class to let the base class and Windows respond to the message.  
  
 In all cases, put the function prototype in the `CWnd`\-derived class header, and code the message map entry as shown.  
  
 The following terms are used:  
  
|용어|정의|  
|--------|--------|  
|id|Any user\-defined menu item ID \(**WM\_COMMAND** messages\) or control ID \(child window notification messages\).|  
|"message" and "wNotifyCode"|Windows message IDs as defined in WINDOWS.H.|  
|nMessageVariable|Name of a variable that contains the return value from the **RegisterWindowMessage** Windows function.|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)