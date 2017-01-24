---
title: "Windows 소켓: CAsyncSocket 클래스 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAsyncSocket 클래스, 프로그래밍 모델"
  - "SOCKET 핸들"
  - "소켓[C++], 비동기 작업"
  - "소켓[C++], 유니코드와 MBCS 문자열 간 변환"
  - "Windows 소켓[C++], 비동기"
  - "Windows 소켓[C++], 유니코드와 MBCS 문자열 변환"
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓: CAsyncSocket 클래스 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains how to use class [CAsyncSocket](../mfc/reference/casyncsocket-class.md).  Be aware that this class encapsulates the Windows Sockets API at a very low level.  `CAsyncSocket` is for use by programmers who know network communications in detail but want the convenience of callbacks for notification of network events.  Based on this assumption, this article provides only basic instruction.  You should probably consider using `CAsyncSocket` if you want Windows Sockets' ease of dealing with multiple network protocols in an MFC application but do not want to sacrifice flexibility.  You might also feel that you can get better efficiency by programming the communications more directly yourself than you could using the more general alternative model of class `CSocket`.  
  
 `CAsyncSocket` is documented in the *MFC Reference*.  Visual C\+\+ also supplies the Windows Sockets specification, located in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  The details are left to you.  Visual C\+\+ does not supply a sample application for `CAsyncSocket`.  
  
 If you are not highly knowledgeable about network communications and want a simple solution, use class [CSocket](../mfc/reference/csocket-class.md) with a `CArchive` object.  See [Windows Sockets: Using Sockets with Archives](../mfc/windows-sockets-using-sockets-with-archives.md) for more information.  
  
 This article covers:  
  
-   Creating and using a `CAsyncSocket` object.  
  
-   [Your responsibilities with CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Creating and Using a CAsyncSocket Object  
  
#### To use CAsyncSocket  
  
1.  Construct a [CAsyncSocket](../mfc/reference/casyncsocket-class.md) object and use the object to create the underlying **SOCKET** handle.  
  
     Creation of a socket follows the MFC pattern of two\-stage construction.  
  
     예를 들면 다음과 같습니다.  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/CPP/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     또는  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/CPP/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     The first constructor above creates a `CAsyncSocket` object on the stack.  The second constructor creates a `CAsyncSocket` on the heap.  The first [Create](../Topic/CAsyncSocket::Create.md) call above uses the default parameters to create a stream socket.  The second **Create** call creates a datagram socket with a specified port and address. \(You can use either **Create** version with either construction method.\)  
  
     The parameters to **Create** are:  
  
    -   A "port": a short integer.  
  
         For a server socket, you must specify a port.  For a client socket, you typically accept the default value for this parameter, which lets Windows Sockets select a port.  
  
    -   A socket type: **SOCK\_STREAM** \(the default\) or **SOCK\_DGRAM**.  
  
    -   A socket "address," such as "ftp.microsoft.com" or "128.56.22.8".  
  
         This is your Internet Protocol \(IP\) address on the network.  You will probably always rely on the default value for this parameter.  
  
     The terms "port" and "socket address" are explained in [Windows Sockets: Ports and Socket Addresses](../mfc/windows-sockets-ports-and-socket-addresses.md).  
  
2.  If the socket is a client, connect the socket object to a server socket, using [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md).  
  
     또는  
  
     If the socket is a server, set the socket to begin listening \(with [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)\) for connect attempts from a client.  Upon receiving a connection request, accept it with [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md).  
  
     After accepting a connection, you can perform such tasks as validating passwords.  
  
    > [!NOTE]
    >  The **Accept** member function takes a reference to a new, empty `CSocket` object as its parameter.  You must construct this object before you call **Accept**.  If this socket object goes out of scope, the connection closes.  Do not call **Create** for this new socket object.  For an example, see the article [Windows Sockets: Sequence of Operations](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Carry out communications with other sockets by calling the `CAsyncSocket` object's member functions that encapsulate the Windows Sockets API functions.  
  
     See the Windows Sockets specification and class [CAsyncSocket](../mfc/reference/casyncsocket-class.md) in the *MFC Reference*.  
  
4.  Destroy the `CAsyncSocket` object.  
  
     If you created the socket object on the stack, its destructor is called when the containing function goes out of scope.  If you created the socket object on the heap, using the **new** operator, you are responsible for using the **delete** operator to destroy the object.  
  
     The destructor calls the object's [Close](../Topic/CAsyncSocket::Close.md) member function before destroying the object.  
  
 For an example of this sequence in code \(actually for a `CSocket` object\), see [Windows Sockets: Sequence of Operations](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Your Responsibilities with CAsyncSocket  
 When you create an object of class [CAsyncSocket](../mfc/reference/casyncsocket-class.md), the object encapsulates a Windows **SOCKET** handle and supplies operations on that handle.  When you use `CAsyncSocket`, you must deal with all the issues you might face if using the API directly.  예를 들면 다음과 같습니다.  
  
-   "Blocking" scenarios.  
  
-   Byte order differences between the sending and receiving machines.  
  
-   Converting between Unicode and multibyte character set \(MBCS\) strings.  
  
 For definitions of these terms and additional information, see [Windows Sockets: Blocking](../mfc/windows-sockets-blocking.md), [Windows Sockets: Byte Ordering](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets: Converting Strings](../mfc/windows-sockets-converting-strings.md).  
  
 Despite these issues, class **CAsycnSocket** may be the right choice for you if your application requires all the flexibility and control you can get.  If not, you should consider using class `CSocket` instead.  `CSocket` hides a lot of detail from you: it pumps Windows messages during blocking calls and gives you access to `CArchive`, which manages byte order differences and string conversion for you.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows Sockets: Background](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagram Sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)