---
title: "일반적인 Gopher 클라이언트 응용 프로그램의 단계 | Microsoft Docs"
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
  - "Gopher 클라이언트 응용 프로그램"
  - "인터넷 응용 프로그램, gopher 클라이언트 응용 프로그램"
  - "인터넷 클라이언트 응용 프로그램, gopher 테이블"
  - "WinInet 클래스, gopher"
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 일반적인 Gopher 클라이언트 응용 프로그램의 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows the steps you might perform in a typical gopher client application.  
  
|Your goal|Actions you take|효과|  
|---------------|----------------------|--------|  
|Begin a gopher session.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Initializes WinInet and connects to server.|  
|Connect to a gopher server.|Use [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).|Returns a [CGopherConnection](../mfc/reference/cgopherconnection-class.md) object.|  
|Find the first resource in the gopher.|Use [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).|Finds the first file.  Returns FALSE if no files are found.|  
|Find the next resource in the gopher.|Use [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md).|Finds the next file.  Returns FALSE if the file is not found.|  
|Open the file found by **FindFile** or `FindNextFile` for reading.|Get a gopher locator using [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Use [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Opens the file specified by the locator.  `OpenFile` returns a [CGopherFile](../mfc/reference/cgopherfile-class.md) object.|  
|Open a file using a gopher locator you supply.|Create a gopher locator using [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md).  Use [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Opens the file specified by the locator.  `OpenFile` returns a [CGopherFile](../mfc/reference/cgopherfile-class.md) object.|  
|Read from the file.|Use [CGopherFile](../mfc/reference/cgopherfile-class.md).|Reads the specified number of bytes, using a buffer you supply.|  
|예외 처리|Use the [CInternetException](../mfc/reference/cinternetexception-class.md) class.|Handles all common Internet exception types.|  
|End the gopher session.|Dispose of the [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Automatically cleans up open file handles and connections.|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)