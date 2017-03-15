---
title: "MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성 | Microsoft Docs"
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
  - "인터넷 응용 프로그램, 클라이언트 응용 프로그램"
  - "인터넷 응용 프로그램, WinInet"
  - "인터넷 클라이언트 응용 프로그램"
  - "인터넷 클라이언트 응용 프로그램, 작성"
  - "MFC, 인터넷 응용 프로그램"
  - "WinInet 클래스, 프로그래밍"
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The basis of every Internet client application is the Internet session.  MFC implements Internet sessions as objects of class [CInternetSession](../mfc/reference/cinternetsession-class.md).  Using this class, you can create one Internet session or several simultaneous sessions.  
  
 To communicate with a server, you need a [CInternetConnection](../mfc/reference/cinternetconnection-class.md) object as well as a `CInternetSession`.  You can create a `CInternetConnection` by using [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), or [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).  Each of these calls is specific to the protocol type.  These calls do not open a file on the server for reading or writing.  If you intend to read or write data, you must open the file as a separate step.  
  
 For most Internet sessions, the `CInternetSession` object works hand\-in\-hand with a [CInternetFile](../mfc/reference/cinternetfile-class.md) object:  
  
-   For an Internet session, you must create an instance of [CInternetSession](../mfc/reference/cinternetsession-class.md).  
  
-   If your Internet session reads or writes data, you must create an instance of `CInternetFile` \(or its subclasses, [CHttpFile](../mfc/reference/chttpfile-class.md) or [CGopherFile](../mfc/reference/cgopherfile-class.md)\).  The easiest way to read data is to call [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  This function parses a Universal Resource Locator \(URL\) supplied by you, opens a connection to the server specified by the URL, and returns a read\-only `CInternetFile` object.  `CInternetSession::OpenURL` is not specific to one protocol type — the same call works for any FTP, HTTP, or gopher URL.  `CInternetSession::OpenURL` even works with local files \(returning a `CStdioFile` instead of a `CInternetFile`\).  
  
-   If your Internet session does not read or write data, but performs other tasks, such as deleting a file in an FTP directory, you may not need to create an instance of `CInternetFile`.  
  
 There are two ways to create a `CInternetFile` object:  
  
-   If you use `CInternetSession::OpenURL` to establish your server connection, the call to `OpenURL` returns a `CStdioFile`.  
  
-   If use **CInternetSession::GetFtpConnection**, `GetGopherConnection`, or `GetHttpConnection` to establish your server connection, you must call `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, or **CHttpConnection::OpenRequest,** respectively, to return a `CInternetFile`, `CGopherFile`, or `CHttpFile`, respectively.  
  
 The steps in implementing an Internet client application vary depending on whether you create a generic Internet client based on **OpenURL** or a protocol\-specific client using one of the **GetConnection** functions.  
  
## 추가 정보  
  
-   [How do I write an Internet client application that works generically with FTP, HTTP, and gopher?](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [How do I write an FTP client application that opens a file?](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [How do I write an FTP client application that does not open a file but performs a directory operation, such as deleting a file?](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [How do I write a gopher client application?](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [How do I write an HTTP client application?](../mfc/steps-in-a-typical-http-client-application.md)  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)