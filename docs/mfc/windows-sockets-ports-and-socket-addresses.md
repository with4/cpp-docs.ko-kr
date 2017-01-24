---
title: "Windows 소켓: 포트 및 소켓 주소 | Microsoft Docs"
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
  - "주소[C++], 소켓"
  - "포트[C++]"
  - "포트[C++], 정의"
  - "소켓[C++], 주소"
  - "소켓[C++], 포트"
  - "Windows 소켓[C++], 주소"
  - "Windows 소켓[C++], 포트"
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓: 포트 및 소켓 주소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains the terms "port" and "address" as used with Windows Sockets.  
  
##  <a name="_core_port"></a> 포트  
 A port identifies a unique process for which a service can be provided.  In the present context, a port is associated with an application that supports Windows Sockets.  The idea is to identify each Windows Sockets application uniquely so you can have more than one Windows Sockets application running on a machine at the same time.  
  
 Certain ports are reserved for common services, such as FTP.  You should avoid using those ports unless you are providing that kind of service.  The Windows Sockets specification details these reserved ports.  The file WINSOCK.H also lists them.  
  
 To let the Windows Sockets DLL select a usable port for you, pass 0 as the port value.  MFC selects a port value greater than 1,024 decimal.  You can retrieve the port value that MFC selected by calling the [CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md) member function.  
  
##  <a name="_core_socket_address"></a> Socket Address  
 Each socket object is associated with an Internet Protocol \(IP\) address on the network.  Typically, the address is a machine name, such as "ftp.microsoft.com", or a dotted number, such as "128.56.22.8".  
  
 When you seek to create a socket, you typically do not need to specify your own address.  
  
> [!NOTE]
>  It is possible that your machine has multiple network cards \(or your application might someday run on such a machine\), each representing a different network.  If so, you might need to give an address to specify which network card the socket will use.  This is certain to be an advanced usage and a possible portability issue.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: How Sockets with Archives Work](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagram Sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)