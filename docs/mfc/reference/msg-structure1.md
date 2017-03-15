---
title: "MSG 구조&amp;1; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSG 구조체"
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MSG 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `MSG` structure contains message information from a thread's message queue.  
  
## 구문  
  
```  
  
      typedef struct tagMSG {     // msg    
   HWND hwnd;  
   UINT message;  
   WPARAM wParam;  
   LPARAM lParam;  
   DWORD time;  
   POINT pt;  
} MSG;  
```  
  
#### 매개 변수  
 *hwnd*  
 Identifies the window whose window procedure receives the message.  
  
 `message`  
 Specifies the message number.  
  
 `wParam`  
 Specifies additional information about the message.  The exact meaning depends on the value of the **message** member.  
  
 `lParam`  
 Specifies additional information about the message.  The exact meaning depends on the value of the **message** member.  
  
 `time`  
 Specifies the time at which the message was posted.  
  
 `pt`  
 Specifies the cursor position, in screen coordinates, when the message was posted.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)