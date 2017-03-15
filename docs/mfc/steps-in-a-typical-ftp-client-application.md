---
title: "일반적인 FTP 클라이언트 응용 프로그램의 단계 | Microsoft Docs"
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
  - "FTP(파일 전송 프로토콜)"
  - "FTP(파일 전송 프로토콜), 클라이언트 응용 프로그램"
  - "인터넷 응용 프로그램, FTP 클라이언트 응용 프로그램"
  - "인터넷 클라이언트 응용 프로그램, FTP 테이블"
  - "WinInet 클래스, FTP"
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 일반적인 FTP 클라이언트 응용 프로그램의 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A typical FTP client application creates a [CInternetSession](../mfc/reference/cinternetsession-class.md) and a [CFtpConnection](../mfc/reference/cftpconnection-class.md) object.  Note that these MFC WinInet classes do not actually control the proxy type settings; IIS does.  
  
 Also, see these Knowledge Base articles:  
  
-   HOWTO: FTP with CERN\-Based Proxy Using WinInet API \(Article ID: Q166961\)  
  
-   SAMPLE: FTP with CERN\-Based Password Protected Proxy \(Article ID: Q216214\)  
  
-   Internet Services Manager Fails to Show Installed Proxy Services \(Article ID: Q216802\)  
  
 The following table shows the steps you might perform in a typical FTP client application.  
  
|Your goal|Actions you take|효과|  
|---------------|----------------------|--------|  
|Begin an FTP session.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Initializes WinInet and connects to server.|  
|Connect to an FTP server.|Use [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|Returns a [CFtpConnection](../mfc/reference/cftpconnection-class.md) object.|  
|Change to a new FTP directory on the server.|Use [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Changes the directory you are currently connected to on the server.|  
|Find the first file in the FTP directory.|Use [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Finds the first file.  Returns FALSE if no files are found.|  
|Find the next file in the FTP directory.|Use [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Finds the next file.  Returns FALSE if the file is not found.|  
|Open the file found by **FindFile** or `FindNextFile` for reading or writing.|Use [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md), using the file name returned by [FindFile](../Topic/CFtpFileFind::FindFile.md) or [FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Opens the file on the server for reading or writing.  Returns a [CInternetFile](../mfc/reference/cinternetfile-class.md) object.|  
|Read from or write to the file.|Use [CInternetFile::Read](../Topic/CInternetFile::Read.md) or [CInternetFile::Write](../Topic/CInternetFile::Write.md).|Reads or writes the specified number of bytes, using a buffer you supply.|  
|예외 처리|Use the [CInternetException](../mfc/reference/cinternetexception-class.md) class.|Handles all common Internet exception types.|  
|End the FTP session.|Dispose of the [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Automatically cleans up open file handles and connections.|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)