---
title: "인터넷 클라이언트 클래스의 필수 구성 요소 | Microsoft Docs"
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
  - "클래스[C++], 연결"
  - "연결[C++], 클래스"
  - "파일[C++], 읽기"
  - "파일[C++], 쓰기"
  - "FTP(파일 전송 프로토콜), MFC 클래스"
  - "Gopher 클라이언트 응용 프로그램"
  - "Gopher 필수 구성 요소"
  - "HTTP, 인터넷 클라이언트 필수 구성 요소"
  - "인터넷[C++], 연결"
  - "인터넷 클라이언트 클래스 필수 구성 요소[C++]"
  - "인터넷 파일[C++], 쓰기"
  - "필수 구성 요소, 인터넷 클라이언트 클래스"
  - "URL[C++], 인터넷 클라이언트 응용 프로그램"
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 인터넷 클라이언트 클래스의 필수 구성 요소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Some actions taken by an Internet client \(reading a file, for example\) have prerequisite actions \(in this case, establishing an Internet connection\).  The following tables list the prerequisites for some client actions.  
  
### General Internet URL \(FTP, Gopher, or HTTP\)  
  
|작업|Prerequisite|  
|--------|------------------|  
|Establish a connection.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) to establish the basis of an Internet client application.|  
|Open a URL.|Establish a connection.  Call [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  The `OpenURL` function returns a read\-only resource object.|  
|Read URL data.|Open the URL.  Call [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Set an Internet option.|Establish a connection.  Call [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|  
|Set a function to be called with status information.|Establish a connection.  Call [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).  Override [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) to handle calls.|  
  
### FTP  
  
|작업|Prerequisite|  
|--------|------------------|  
|Establish an FTP connection.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) as the basis of this Internet client application.  Call [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md) to create a [CFtpConnection](../mfc/reference/cftpconnection-class.md) object.|  
|Find the first resource.|Establish an FTP connection.  Create a [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) object.  Call [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|  
|Enumerate all available resources.|Find the first file.  Call [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md) until it returns FALSE.|  
|Open an FTP file.|Establish an FTP connection.  Call [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md) to create and open a [CInternetFile](../mfc/reference/cinternetfile-class.md) object.|  
|Read an FTP file.|Open an FTP file with read access.  Call [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Write to an FTP file.|Open an FTP file with write access.  Call [CInternetFile::Write](../Topic/CInternetFile::Write.md).|  
|Change the client's directory on the server.|Establish an FTP connection.  Call [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|  
|Retrieve the client's current directory on the server.|Establish an FTP connection.  Call [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md).|  
  
### HTTP  
  
|작업|Prerequisite|  
|--------|------------------|  
|Establish an HTTP connection.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) as the basis of this Internet client application.  Call [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) to create a [CHttpConnection](../mfc/reference/chttpconnection-class.md) object.|  
|Open an HTTP file.|Establish an HTTP connection.  Call [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) to create a [CHttpFile](../mfc/reference/chttpfile-class.md) object.  Call [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md).  Call [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|  
|Read an HTTP file.|Open an HTTP file.  Call [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Get information about an HTTP request.|Establish an HTTP connection.  Call [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) to create a [CHttpFile](../mfc/reference/chttpfile-class.md) object.  Call [CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md).|  
  
### Gopher  
  
|작업|Prerequisite|  
|--------|------------------|  
|Establish a gopher connection.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) as the basis of this Internet client application.  Call [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) to create a [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Find the first file in the current directory.|Establish a gopher connection.  Create a [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) object.  Call [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) to create a [CGopherLocator](../mfc/reference/cgopherlocator-class.md) object.  Pass the locator to [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).  Call [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md) to get the locator of a file if you need it later.|  
|Enumerate all available files.|Find the first file.  Call [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md) until it returns FALSE.|  
|Open a gopher file.|Establish a gopher connection.  Create a gopher locator with [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) or find a locator with [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Call [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|  
|Read a gopher file.|Open a gopher file.  Use [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)