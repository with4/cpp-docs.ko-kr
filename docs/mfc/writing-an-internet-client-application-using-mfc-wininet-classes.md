---
title: "MFC WinInet 클래스를 사용 하 여 인터넷 클라이언트 응용 프로그램 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07b97d4af18ff560a48aadb3ba71b61609f82a85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성
모든 인터넷 클라이언트 응용 프로그램의 기본은 인터넷 세션입니다. 클래스의 개체로 인터넷 세션을 구현 하는 MFC [CInternetSession](../mfc/reference/cinternetsession-class.md)합니다. 이 클래스를 사용 하 여 하나의 인터넷 세션 또는 여러 개의 동시 세션을 만들 수 있습니다.  
  
 서버와 통신 하려면는 [CInternetConnection](../mfc/reference/cinternetconnection-class.md) 개체와 함께 `CInternetSession`합니다. 만들 수는 `CInternetConnection` 를 사용 하 여 [cinternetsession:: Getftpconnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), 또는 [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). 이러한 호출의 각 프로토콜 형식에 해당 됩니다. 이러한 호출은 읽기 또는 쓰기에 대 한 서버에서 파일을 열지 마십시오. 데이터를 읽거나 하려는 경우 별도 단계로 파일을 열어야 합니다.  
  
 대부분의 인터넷 세션에 대 한는 `CInternetSession` 를 손에서 직접 작동 하는 개체는 [CInternetFile](../mfc/reference/cinternetfile-class.md) 개체:  
  
-   인스턴스는 인터넷 세션에 대 한 만들어야 [CInternetSession](../mfc/reference/cinternetsession-class.md)합니다.  
  
-   인스턴스의 경우 인터넷 세션에서 읽거나 쓸 데이터를 만들어야 `CInternetFile` (또는 해당 서브 클래스 [CHttpFile](../mfc/reference/chttpfile-class.md) 또는 [CGopherFile](../mfc/reference/cgopherfile-class.md)). 호출 하는 데이터를 읽을 수는 가장 쉬운 방법은 것 [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl)합니다. 이 함수는 범용 URL (Resource Locator)가 제공을 구문 분석의 URL에서 지정한 서버에 연결 하 고 읽기 전용 반환 `CInternetFile` 개체입니다. `CInternetSession::OpenURL`하나의 프로토콜 형식과 관련 된-모든 FTP, HTTP, 또는 gopher URL에 대해 작동 하는 동일한 호출 합니다. `CInternetSession::OpenURL`로컬 파일에도 작동 (반환는 `CStdioFile` 대신는 `CInternetFile`).  
  
-   인스턴스를 만드는 필요 하지 않을 수 있습니다 세션 읽이 되지 않거나 데이터를 쓰는 인터넷 하지만 FTP 디렉터리의 파일을 삭제 하는 등의 다른 작업을 수행 하는 경우 `CInternetFile`합니다.  
  
 두 가지 방법으로 만들 수는 `CInternetFile` 개체:  
  
-   사용 하는 경우 `CInternetSession::OpenURL` 서버 연결에 대 한 호출을 설정 하려면 `OpenURL` 반환는 `CStdioFile`합니다.  
  
-   하는 경우 사용 하 여 **cinternetsession:: Getftpconnection**, `GetGopherConnection`, 또는 `GetHttpConnection` 서버 연결을 설정 하려면 `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, 또는 **CHttpConnection::OpenRequest,**  각각 반환 하는 `CInternetFile`, `CGopherFile`, 또는 `CHttpFile`각각.  
  
 인터넷 클라이언트 응용 프로그램을 구현할의 단계에 따라 일반 인터넷 클라이언트를 만드는 지에 따라 다를 **OpenURL** 중 하나를 사용 하는 프로토콜 관련 클라이언트는 **GetConnection** 함수입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [FTP, HTTP 및 gopher 일반적으로 사용 하는 인터넷 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [파일을 FTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [파일이 열리지 않고 하지만 파일을 삭제 하는 등 디렉터리 작업을 수행 하는 FTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Gopher 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [HTTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-http-client-application.md)  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)
