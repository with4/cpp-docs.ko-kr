---
title: "Windows 소켓: 작업 순서 | Microsoft Docs"
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
  - "소켓[C++], 작업"
  - "소켓[C++], 스트림 소켓"
  - "스트림 소켓[C++]"
  - "Windows 소켓[C++], 작업"
  - "Windows 소켓[C++], 스트림 소켓"
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓: 작업 순서
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article illustrates, side by side, the sequence of operations for a server socket and a client socket.  Because the sockets use `CArchive` objects, they are necessarily [stream sockets](../mfc/windows-sockets-stream-sockets.md).  
  
## Sequence of Operations for a Stream Socket Communication  
 Up to the point of constructing a `CSocketFile` object, the following sequence is accurate \(with a few parameter differences\) for both `CAsyncSocket` and `CSocket`.  From that point on, the sequence is strictly for `CSocket`.  The following table illustrates the sequence of operations for setting up communication between a client and a server.  
  
### Setting Up Communication Between a Server and a Client  
  
|서버|클라이언트|  
|--------|-----------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> 또는<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> – or Both –|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> 또는<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> – or Both –|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> 또는<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> 또는<br /><br /> `arOut << dwValue;`6|  
  
 1.  Where `nPort` is a port number.  See [Windows Sockets: Ports and Socket Addresses](../mfc/windows-sockets-ports-and-socket-addresses.md) for details about ports.  
  
 2.  The server must always specify a port so clients can connect.  The **Create** call sometimes also specifies an address.  On the client side, use the default parameters, which ask MFC to use any available port.  
  
 3.  Where `nPort` is a port number and *strAddr* is a machine address or an Internet Protocol \(IP\) address.  
  
 4.  Machine addresses can take several forms: "ftp.microsoft.com", "microsoft.com".  IP addresses use the "dotted number" form "127.54.67.32".  The **Connect** function checks to see if the address is a dotted number \(although it does not check to ensure the number is a valid machine on the network\).  If not, **Connect** assumes a machine name of one of the other forms.  
  
 5.  When you call **Accept** on the server side, you pass a reference to a new socket object.  You must construct this object first, but do not call **Create** for it.  Keep in mind that if this socket object goes out of scope, the connection closes.  MFC connects the new object to a **SOCKET** handle.  You can construct the socket on the stack, as shown, or on the heap.  
  
 6.  The archive and the socket file are closed when they go out of scope.  The socket object's destructor also calls the [Close](../Topic/CAsyncSocket::Close.md) member function for the socket object when the object goes out of scope or is deleted.  
  
## Additional Notes About the Sequence  
 The sequence of calls shown in the preceding table is for a stream socket.  Datagram sockets, which are connectionless, do not require the [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md), [Listen](../Topic/CAsyncSocket::Listen.md), and [Accept](../Topic/CAsyncSocket::Accept.md) calls \(although you can optionally use **Connect**\).  Instead, if you are using class `CAsyncSocket`, datagram sockets use the `CAsyncSocket::SendTo` and `ReceiveFrom` member functions. \(If you use **Connect** with a datagram socket, you use **Send** and **Receive**.\) Because `CArchive` does not work with datagrams, do not use `CSocket` with an archive if the socket is a datagram.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) does not support all of `CFile`'s functionality; `CFile` members such as `Seek`, which make no sense for a socket communication, are unavailable.  Because of this, some default MFC `Serialize` functions are not compatible with `CSocketFile`.  This is particularly true of the `CEditView` class.  You should not try to serialize `CEditView` data through a `CArchive` object attached to a `CSocketFile` object using `CEditView::SerializeRaw`; use **CEditView::Serialize** instead \(not documented\).  The [SerializeRaw](../Topic/CEditView::SerializeRaw.md) function expects the file object to have functions, such as `Seek`, that `CSocketFile` does not support.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Ports and Socket Addresses](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagram Sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [CSocket Class](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)