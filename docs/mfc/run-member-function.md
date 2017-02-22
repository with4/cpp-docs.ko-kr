---
title: "Run 멤버 함수 | Microsoft Docs"
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
  - "CWinApp 클래스, Run"
  - "CWinApp::Run의 메시지 펌프"
  - "메시지, 루프"
  - "Run 메서드, 메시지 및 유휴 프로세스"
  - "WinMain 메서드"
  - "WinMain 메서드, CWinApp::Run 호출"
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Run 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A framework application spends most of its time in the [Run](../Topic/CWinApp::Run.md) member function of class [CWinApp](../mfc/reference/cwinapp-class.md).  After initialization, `WinMain` calls **Run** to process the message loop.  
  
 **Run** cycles through a message loop, checking the message queue for available messages.  If a message is available, **Run** dispatches it for action.  If no messages are available, which is often true, **Run** calls `OnIdle` to do any idle\-time processing that you or the framework may need done.  If there are no messages and no idle processing to do, the application waits until something happens.  When the application terminates, **Run** calls `ExitInstance`.  The figure in [OnIdle Member Function](../mfc/onidle-member-function.md) shows the sequence of actions in the message loop.  
  
 Message dispatching depends on the kind of message.  For more information, see [Messages and Commands in the Framework](../mfc/messages-and-commands-in-the-framework.md).  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)