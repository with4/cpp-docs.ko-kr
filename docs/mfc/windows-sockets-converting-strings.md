---
title: "Windows 소켓: 문자열 변환 | Microsoft Docs"
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
  - "소켓[C++], 멀티바이트 문자열 변환 문제"
  - "문자열 변환, 멀티바이트 문자열"
  - "Windows 소켓[C++], 멀티바이트 문자열 변환"
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows 소켓: 문자열 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article and two companion articles explain several issues in Windows Sockets programming.  This article covers converting strings.  The other issues are covered in [Windows Sockets: Blocking](../mfc/windows-sockets-blocking.md) and [Windows Sockets: Byte Ordering](../mfc/windows-sockets-byte-ordering.md).  
  
 If you use or derive from class [CAsyncSocket](../mfc/reference/casyncsocket-class.md), you will need to manage these issues yourself.  If you use or derive from class [CSocket](../mfc/reference/csocket-class.md), MFC manages them for you.  
  
## Converting Strings  
 If you communicate between applications that use strings stored in different wide\-character formats, such as Unicode or multibyte character sets \(MBCS\), or between one of these and an application using ANSI character strings, you must manage the conversions yourself under `CAsyncSocket`.  The `CArchive` object used with a `CSocket` object manages this conversion for you through the capabilities of class [CString](../atl-mfc-shared/reference/cstringt-class.md).  For more information, see the Windows Sockets specification, located in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Background](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagram Sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)