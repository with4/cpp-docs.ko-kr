---
title: "Windows 소켓: 데이터그램 소켓 | Microsoft Docs"
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
  - "데이터그램 소켓[C++]"
  - "소켓[C++], 양방향 데이터 흐름"
  - "소켓[C++], 데이터그램"
  - "Windows 소켓[C++], 양방향 데이터 흐름"
  - "Windows 소켓[C++], 데이터그램"
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Windows 소켓: 데이터그램 소켓
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes datagram sockets, one of the two Windows Socket types available. \(The other type is the [stream socket](../mfc/windows-sockets-stream-sockets.md).\)  
  
 Datagram sockets support a bidirectional data flow that is not guaranteed to be sequenced or unduplicated.  Datagrams also are not guaranteed to be reliable; they can fail to arrive.  Datagram data may arrive out of order and possibly duplicated, but record boundaries in the data are preserved, as long as the records are smaller than the receiver's internal size limit.  You are responsible for managing sequencing and reliability. \(Reliability tends to be good on local\-area networks \[LAN\] but less so on wide\-area networks \[WAN\], such as the Internet.\)  
  
 Datagrams are "connectionless", that is, no explicit connection is established; you send a datagram message to a specified socket and you can receive messages from a specified socket.  
  
 An example of a datagram socket is an application that keeps system clocks on the network synchronized.  This illustrates an additional capability of datagram sockets in at least some settings: broadcasting messages to a large number of network addresses.  
  
 Datagram sockets are better than stream sockets for record\-oriented data.  For more information about datagram sockets, see the Windows Sockets specification, available in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)