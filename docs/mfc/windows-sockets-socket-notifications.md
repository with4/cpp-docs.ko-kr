---
title: "Windows 소켓: 소켓 알림 | Microsoft Docs"
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
  - "알림, 소켓"
  - "소켓[C++], 알림"
  - "Windows 소켓[C++], 알림"
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Windows 소켓: 소켓 알림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes the notification functions in the socket classes.  These member functions are callback functions that the framework calls to notify your socket object of important events.  The notification functions are:  
  
-   [OnReceive](../Topic/CAsyncSocket::OnReceive.md): Notifies this socket that there is data in the buffer for it to retrieve by calling [Receive](../Topic/CAsyncSocket::Receive.md).  
  
-   [OnSend](../Topic/CAsyncSocket::OnSend.md): Notifies this socket that it can now send data by calling [Send](../Topic/CAsyncSocket::Send.md).  
  
-   [OnAccept](../Topic/CAsyncSocket::OnAccept.md): Notifies this listening socket that it can accept pending connection requests by calling [Accept](../Topic/CAsyncSocket::Accept.md).  
  
-   [OnConnect](../Topic/CAsyncSocket::OnConnect.md): Notifies this connecting socket that its connection attempt completed: perhaps successfully or perhaps in error.  
  
-   [OnClose](../Topic/CAsyncSocket::OnClose.md): Notifies this socket that the socket it is connected to has closed.  
  
    > [!NOTE]
    >  An additional notification function is [OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md).  This notification tells the receiving socket that the sending socket has "out\-of\-band" data to send.  Out\-of\-band data is a logically independent channel associated with each pair of connected stream sockets.  The out\-of\-band channel is typically used to send "urgent" data.  MFC supports out\-of\-band data.  Advanced users working with class [CAsyncSocket](../mfc/reference/casyncsocket-class.md) might need to use the out\-of\-band channel, but users of class [CSocket](../mfc/reference/csocket-class.md) are discouraged from using it.  The easier way is to create a second socket for passing such data.  For more information about out\-of\-band data, see the Windows Sockets specification, available in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 If you derive from class `CAsyncSocket`, you must override the notification functions for those network events of interest to your application.  If you derive a class from class `CSocket`, it is your choice whether to override the notification functions of interest.  You can also use `CSocket` itself, in which case the notification functions default to doing nothing.  
  
 These functions are overridable callback functions.  `CAsyncSocket` and `CSocket` convert messages to notifications, but you must implement how the notification functions respond if you wish to use them.  The notification functions are called at the time your socket is notified of an event of interest, such as the presence of data to be read.  
  
 MFC calls the notification functions to let you customize your socket's behavior at the time it is notified.  For example, you might call **Receive** from your `OnReceive` notification function, that is, on being notified that there is data to read, you call **Receive** to read it.  This approach is not necessary, but it is a valid scenario.  As an alternative, you might use your notification function to track progress, print **TRACE** messages, and so on.  
  
 You can take advantage of these notifications by overriding the notification functions in a derived socket class and providing an implementation.  
  
 During an operation such as receiving or sending data, a `CSocket` object becomes synchronous.  During the synchronous state, any notifications meant for other sockets are queued while the current socket waits for the notification it wants. \(For example, during a **Receive** call, the socket wants a notification to read.\) Once the socket completes its synchronous operation and becomes asynchronous again, other sockets can begin receiving the queued notifications.  
  
> [!NOTE]
>  In `CSocket`, the `OnConnect` notification function is never called.  For connections, you call **Connect**, which will return when the connection is completed \(either successfully or in error\).  How connection notifications are handled is an MFC implementation detail.  
  
 For details about each notification function, see the function under class `CAsyncSocket` in the *MFC Reference*.  For source code and information about MFC samples, see [MFC Samples](../top/visual-cpp-samples.md).  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Deriving from Socket Classes](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets: How Sockets with Archives Work](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Blocking](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets: Byte Ordering](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets: Converting Strings](../mfc/windows-sockets-converting-strings.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)