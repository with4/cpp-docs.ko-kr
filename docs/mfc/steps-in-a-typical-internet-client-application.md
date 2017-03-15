---
title: "일반적인 인터넷 클라이언트 응용 프로그램의 단계 | Microsoft Docs"
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
  - "인터넷 클라이언트 응용 프로그램, 일반 테이블"
  - "WinInet 클래스, 프로그래밍"
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 일반적인 인터넷 클라이언트 응용 프로그램의 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows the steps you might perform in a typical Internet client application.  
  
|Your goal|Actions you take|효과|  
|---------------|----------------------|--------|  
|Begin an Internet session.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Initializes WinInet and connects to server.|  
|Set an Internet query option \(time\-out limit or number of retries, for example\).|Use [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|Returns FALSE if operation was unsuccessful.|  
|Establish a callback function to monitor the status of the session.|Use [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).|Establishes a callback to [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md).  Override `OnStatusCallback` to create your own callback routine.|  
|Connect to an Internet server, intranet server, or local file.|Use [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).|Parses the URL and opens a connection to the specified server.  Returns a [CStdioFile](../mfc/reference/cstdiofile-class.md) \(if you pass `OpenURL` a local file name\).  This is the object through which you access data retrieved from the server or file.|  
|Read from the file.|Use [CInternetFile::Read](../Topic/CInternetFile::Read.md).|Reads the specified number of bytes using a buffer you supply.|  
|예외 처리|Use the [CInternetException](../mfc/reference/cinternetexception-class.md) class.|Handles all common Internet exception types.|  
|End the Internet session.|Dispose of the [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Automatically cleans up open file handles and connections.|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)