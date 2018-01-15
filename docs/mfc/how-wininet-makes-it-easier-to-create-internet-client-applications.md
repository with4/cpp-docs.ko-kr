---
title: "WinInet을 사용 방법 인터넷 클라이언트 응용 프로그램을 만드는 쉽게 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c79404f296df09afb177930897064b8455217d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet을 사용하여 인터넷 클라이언트 응용 프로그램을 손쉽게 만드는 방법
Win32 인터넷 확장명 또는 WinInet, gopher, FTP, HTTP 등 공용 인터넷 프로토콜에 대 한 액세스를 제공 합니다. WinInet을 사용 하 여 WinSock, TCP/IP 또는 특정 인터넷 프로토콜의 세부 정보를 처리 하지 않고 프로그래밍, 더 높은 수준에서 인터넷 클라이언트 응용 프로그램을 작성할 수 있습니다. WinInet 친숙 한 Win32 API 인터페이스와 함께 세 가지 프로토콜 모두에 대 한 일관 된 일련의 기능을 제공합니다. 이러한 일관성 기본 프로토콜 (예를 들어 FTP에서 HTTP로) 변경 된 경우 원하는 코드 변경 작업을 최소화 합니다.  
  
 Visual c + +는 두 가지 방법 WinInet을 사용할 수 있습니다. Win32 인터넷 기능을 직접 호출할 수 있습니다 (자세한 내용은 Windows SDK에서 OLE 설명서 참조) 또는 WinInet을 통해 사용할 수는 [MFC WinInet 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)합니다.  
  
 **WinInet을 사용할 수 있습니다.**  
  
-   HTML 페이지를 다운로드 합니다.  
  
     HTTP는 클라이언트 브라우저에 HTML 페이지는 서버에서 전송 하는 데 사용 되는 프로토콜입니다.  
  
-   업로드 또는 파일을 다운로드 하거나 디렉터리 목록을 가져오기 위해 FTP 요청을 보냅니다.  
  
     일반적인 요청은 파일을 다운로드 하려면 익명으로 로그온 합니다.  
  
-   인터넷에 있는 리소스에 액세스 하기 위한 gopher의 메뉴 시스템을 사용 합니다.  
  
     메뉴 항목에는 다른 메뉴, 검색할 수는 인덱싱된 데이터베이스, 뉴스 그룹 또는 파일을 비롯 한 여러 가지 형식이 될 수 있습니다.  
  
 연결을 설정 세 가지 프로토콜 모두에 대 한 서버에 요청을 확인을 연결을 닫습니다.  
  
 **MFC WinInet 클래스를 쉽게 만들기:**  
  
-   하드 드라이브에서 파일을 읽는 것 처럼 쉽게 HTTP, FTP, gopher 서버에서 정보를 읽을 합니다.  
  
-   WinSock 또는 TCP/IP에 직접 프로그래밍 작업 없이 HTTP, FTP 및 gopher 프로토콜을 사용 합니다.  
  
     Win32 인터넷 기능을 사용 하는 개발자는 TCP/IP 또는 Windows 소켓에 익숙하면 필요가 없습니다. 여전히을 프로그래밍 하는 소켓 수준에서 직접 WinSock 및 TCP/IP 프로토콜을 사용 하 여 하지만 인터넷을 통해 액세스 HTTP, FTP, 및 gopher 프로토콜 MFC WinInet 클래스를 사용 하기 쉽게 쉽습니다. 여러 가지 일반적인 작업에 개발자는 특정 프로토콜을 사용 하는지에 대 한 자세한 정보 필요가 없습니다.  
  
 인터넷에 있는 다른 컴퓨터에 클라이언트 컴퓨터에서 수행할 수 있는 많은 작업은 시간이 오래 걸릴 수 있습니다. 이러한 작업의 속도 일반적으로 네트워크 연결 속도로 제한 하지만 다른 네트워크 트래픽과 작업의 복잡성에 의해도 적용 될 수 있습니다. 예를 들어 원격 FTP 서버에 연결 해야 해당 주소를 찾기 위해 해당 서버 이름을 컴퓨터 먼저 한지 합니다. 응용 프로그램의 해당 주소에서 서버에 연결 하려고 시도 합니다. 연결이 열리면 컴퓨터와 원격 서버는 대화를 시작 파일 전송 프로토콜 파일을 검색 하도록 실제로 연결을 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC를 사용하여 인터넷 클라이언트 응용 프로그램을 손쉽게 만드는 방법](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

