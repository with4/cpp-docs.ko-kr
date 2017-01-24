---
title: "Windows 소켓 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.net"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "소켓 클래스"
  - "Windows 소켓[C++], 클래스"
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows Sockets provide a network protocol\-independent way to communicate between two computers.  These sockets can be synchronous \(your program waits until the communication is done\) or asynchronous \(your program continues running while the communication is going on\).  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Encapsulates the Windows Sockets API in a thin wrapper.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Higher level abstraction derived from `CAsyncSocket`.  It operates synchronously.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Provides a `CFile` interface to a Windows Socket.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)