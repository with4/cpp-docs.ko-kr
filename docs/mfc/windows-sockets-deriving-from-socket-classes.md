---
title: "Windows 소켓: 소켓 클래스에서 파생시키기 | Microsoft Docs"
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
  - "파생 클래스, 소켓 클래스에서"
  - "소켓[C++], 소켓 클래스에서 파생"
  - "Windows 소켓[C++], 소켓 클래스에서 파생"
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓: 소켓 클래스에서 파생시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes some of the functionality you can gain by deriving your own class from one of the socket classes.  
  
 You can derive your own socket classes from either [CAsyncSocket](../mfc/reference/casyncsocket-class.md) or [CSocket](../mfc/reference/csocket-class.md) to add your own functionality.  In particular, these classes supply a number of virtual member functions that you can override.  These functions include [OnReceive](../Topic/CAsyncSocket::OnReceive.md), [OnSend](../Topic/CAsyncSocket::OnSend.md), [OnAccept](../Topic/CAsyncSocket::OnAccept.md), [OnConnect](../Topic/CAsyncSocket::OnConnect.md), and [OnClose](../Topic/CAsyncSocket::OnClose.md).  You can override the functions in your derived socket class to take advantage of the notifications they provide when network events occur.  The framework calls these notification callback functions to notify you of important socket events, such as the receipt of data that you can begin reading.  For more information about notification functions, see [Windows Sockets: Socket Notifications](../mfc/windows-sockets-socket-notifications.md).  
  
 Additionally, class `CSocket` supplies the [OnMessagePending](../Topic/CSocket::OnMessagePending.md) member function \(an advanced overridable\).  MFC calls this function while the socket is pumping Windows\-based messages.  You can override `OnMessagePending` to look for particular messages from Windows and respond to them.  
  
 The default version of `OnMessagePending` supplied in class `CSocket` examines the message queue for `WM_PAINT` messages while waiting for a blocking call to complete.  It dispatches paint messages to improve display quality.  Aside from doing something useful, this illustrates one way you might override the function yourself.  As another example, consider using `OnMessagePending` for the following task.  Suppose you display a modeless dialog box while waiting for a network transaction to complete.  The dialog box contains a Cancel button that the user can use to cancel blocking transactions that take too long.  Your `OnMessagePending` override might pump messages related to this modeless dialog box.  
  
 In your `OnMessagePending` override, return either **TRUE** or the return from a call to the base\-class version of `OnMessagePending`.  Call the base\-class version if it performs work that you still want done.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Blocking](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets: Byte Ordering](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets: Converting Strings](../mfc/windows-sockets-converting-strings.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)