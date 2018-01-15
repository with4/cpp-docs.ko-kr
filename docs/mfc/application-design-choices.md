---
title: "응용 프로그램 디자인 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b78c4c086b40f786d86411c99279245704a48a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="application-design-choices"></a>응용 프로그램 디자인 선택
이 문서에는 인터넷에 대 한 프로그래밍 시 고려해 야 할 디자인 문제 중 일부를 설명 합니다.  
  
 이 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [인트라넷 및 인터넷](#_core_intranet_versus_internet)  
  
-   [클라이언트 또는 서버 응용 프로그램](#_core_client_or_server_application)  
  
-   [](#_core_the_web_page)  
  
-   [독립 실행형 응용 프로그램 또는 브라우저](#_core_browser_or_standalone)  
  
-   [인터넷에서 COM](#_core_com_on_the_internet)  
  
-   [클라이언트 데이터 서비스를 다운로드합니다.](#_core_client_data_download_services)  
  
 참조, 이제 프로그램 작성을 시작할 준비가 된 경우 [MFC 응용 프로그램 작성](../mfc/writing-mfc-applications.md)합니다.  
  
##  <a name="_core_intranet_versus_internet"></a>인트라넷 및 인터넷  
 대부분의 응용 프로그램은 인터넷에서 실행 하 고 브라우저와 인터넷에 액세스할 수 있는 모든 사용자에 액세스할 수 있어야 합니다. 기업 인트라넷 TCP/IP 프로토콜을 사용 하는 회사 전체 네트워크 웹 브라우저를 구현 하는 합니다. 인트라넷 회사 전체의 정보는 쉽게 업그레이드할 수 있도록, 중앙 소스를 제공합니다. 소프트웨어 업그레이드에 대 한, 배달 및 설문 조사 불러와, 고객 지원에 대 한 및 정보 배달에 대 한 사용할 수 있습니다. 다음 표에서 인터넷 및 인트라넷의 기능을 비교 합니다.  
  
|인터넷|Intranet|  
|--------------|--------------|  
|낮은 대역폭|높은 대역폭|  
|데이터 및 시스템의 보안을 감소|데이터 및 시스템에 대 한 액세스 제어|  
|콘텐츠의 최소 컨트롤|콘텐츠의 높은 제어|  
  
##  <a name="_core_client_or_server_application"></a>클라이언트 또는 서버 응용 프로그램  
 클라이언트 컴퓨터 또는 서버 컴퓨터에 응용 프로그램이 실행 될 수 있습니다. 응용 프로그램도 서버에 하 고 인터넷을 통해 다운로드 및 클라이언트 컴퓨터에서 실행 합니다. MFC WinInet 클래스 파일을 다운로드 하도록 클라이언트 응용 프로그램에 사용 됩니다. MFC 및 비동기 모니커 클래스 파일을 다운로드 하 고 속성을 제어 하는 데 사용 됩니다. ActiveX 컨트롤 및 액티브 문서에 대 한 클래스는 클라이언트 응용 프로그램 및 클라이언트에서 실행 하려면 서버에서 다운로드 하는 응용 프로그램에 사용 됩니다.  
  
##  <a name="_core_the_web_page"></a>웹 페이지: HTML, 액티브 문서 ActiveX 컨트롤  
 Microsoft 웹 페이지에 콘텐츠를 제공 하는 다양 한 방법을 제공 합니다. 표준 HTML 또는 HTML을 사용할 수 있는 웹 페이지 object 태그 ActiveX 컨트롤과 같은 동적 콘텐츠를 제공 하는 등의 확장입니다.  
  
 웹 브라우저는 일반적으로 HTML 페이지를 표시합니다. 액티브 문서 COM 사용 브라우저의 간단한 포인트 클릭 인터페이스에서 응용 프로그램의 데이터를 표시할 수도 있습니다. 액티브 문서 서버 자체 메뉴 및 도구 모음으로 전체 클라이언트 영역에서 문서, 전체 프레임을 표시할 수 있습니다.  
  
 작성 된 ActiveX 컨트롤을 서버에서 비동기적으로 다운로드 하는 웹 페이지에 표시 합니다. 서버에 정보를 보내기 전에 클라이언트 쪽 유효성 검사를 수행할 VBScript 같은 스크립트 언어를 사용할 수 있습니다.  
  
##  <a name="_core_browser_or_standalone"></a>독립 실행형 응용 프로그램 또는 브라우저  
 HTML 페이지 및 브라우저에서 볼 수 있는 액티브 문서 서버에 포함 된 ActiveX 컨트롤을 작성할 수 있습니다. 웹 서버에서 ISAPI 응용 프로그램을 실행 하는 요청을 전송 하는 단추를 포함 하는 HTML 페이지를 작성할 수 있습니다. 인터넷 프로토콜을 사용 하 여 파일을 다운로드 하 고 브라우저 응용 프로그램을 사용할 필요 없이 사용자에 게 정보를 표시 하는 독립 실행형 응용 프로그램을 작성할 수 있습니다.  
  
##  <a name="_core_com_on_the_internet"></a>인터넷에서 COM  
 ActiveX 컨트롤, 액티브 문서 및 비동기 모니커 모든 COM (구성 요소 개체 모델) 기술을 사용합니다.  
  
 ActiveX 컨트롤 인터넷 사이트에서 문서와 페이지에 동적 콘텐츠를 제공합니다. COM ActiveX 컨트롤 및 액티브 문서를 사용 하 여 전체 프레임 문서를 작성할 수 있습니다.  
  
 비동기 모니커는 증분을 포함 하 여 인터넷 환경에서 제대로 작동 하려면 컨트롤을 사용 하도록 기능을 제공 하거나 데이터를 다운로드할 점진적 의미 합니다. 또한 컨트롤 해야 있습니다 수 데이터를 검색 합니다는 비동기적으로 동시에 다른 컨트롤 제대로 작동 합니다.  
  
##  <a name="_core_client_data_download_services"></a>클라이언트 데이터 서비스를 다운로드합니다.  
 두 클라이언트에 데이터를 전송 하는 데 도움이 되는 Api 집합은 WinInet 및 비동기 모니커입니다. 큰.gif,.avi 파일 및 ActiveX 컨트롤 HTML 페이지를 설정한 경우에 비동기 모니커를 사용 하거나 비동기적으로 WinInet을 사용 하 여 비동기적으로 다운로드 하 여 사용자에 대 한 응답성을 늘릴 수 있습니다.  
  
 인터넷에서 일반적인 작업에 데이터를 전송 합니다. 이미 액티브 기술 (예: ActiveX 컨트롤이 있는 경우)를 사용할 경우 점진적으로 데이터를 렌더링할 다운로드 될 때 비동기 모니커를 사용할 수 있습니다. HTTP, FTP 및 gopher와 같은 일반적인 인터넷 프로토콜을 사용 하 여 데이터를 전송 하도록 WinInet을 사용할 수 있습니다. 두 방법 모두 프로토콜 독립성을 제공 하 고 WinSock와 TCP/IP를 사용 하는 추상 계층을 제공 합니다. 사용할 수 있습니다 [WinSock](../mfc/windows-sockets-in-mfc.md) 직접 합니다.  
  
 다음 표에서 MFC를 사용 하 여 인터넷을 통해 데이터를 전송 하는 여러 가지 방법으로 요약 합니다.  
  
|이 프로토콜을 사용 하 여|이러한 조건|이러한 클래스를 사용 하 여|  
|-----------------------|----------------------------|-------------------------|  
|[인터넷 다운로드를 사용 하 여 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX 컨트롤을 사용 하 여 비동기 전송에 대 한 및의 인터넷 프로토콜.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP, 및 gopher 인터넷 프로토콜. 데이터는 동기적 또는 비동기적으로 전송 될 수 있습니다 및 시스템 수준 캐시에 저장 됩니다.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), 및 기타 다양 합니다.|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|최대 효율성과 제어 합니다. 소켓 또는 TCP/IP 프로토콜이 이해를 해야합니다.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)   
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷의 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)

