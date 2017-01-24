---
title: "일반적인 HTTP 클라이언트 응용 프로그램의 단계 | Microsoft Docs"
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
  - "응용 프로그램[MFC], HTTP 클라이언트"
  - "클라이언트 응용 프로그램[C++], HTTP"
  - "HTTP 클라이언트 응용 프로그램"
  - "인터넷 응용 프로그램[C++], HTTP 클라이언트 응용 프로그램"
  - "인터넷 클라이언트 응용 프로그램[C++], HTTP 테이블"
  - "WinInet 클래스, HTTP"
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 일반적인 HTTP 클라이언트 응용 프로그램의 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows the steps you might perform in a typical HTTP client application:  
  
|Your goal|Actions you take|효과|  
|---------------|----------------------|--------|  
|Begin an HTTP session.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Initializes WinInet and connects to server.|  
|Connect to an HTTP server.|Use [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md).|Returns a [CHttpConnection](../mfc/reference/chttpconnection-class.md) object.|  
|Open an HTTP request.|Use [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).|Returns a [CHttpFile](../mfc/reference/chttpfile-class.md) object.|  
|Send an HTTP request.|Use [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md) and [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|Finds the file.  Returns FALSE if the file is not found.|  
|Read from the file.|Use [CHttpFile](../mfc/reference/chttpfile-class.md).|Reads the specified number of bytes using a buffer you supply.|  
|예외 처리|Use the [CInternetException](../mfc/reference/cinternetexception-class.md) class.|Handles all common Internet exception types.|  
|End the HTTP session.|Dispose of the [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Automatically cleans up open file handles and connections.|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)