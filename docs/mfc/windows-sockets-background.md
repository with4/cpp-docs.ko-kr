---
title: "Windows 소켓: 백그라운드 | Microsoft Docs"
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
  - "통신[C++], 도메인"
  - "데이터 형식[C++], 소켓"
  - "데이터그램 소켓[C++]"
  - "전자 메일[C++]"
  - "전자 메일[C++], 프로그래밍"
  - "인터넷 프로토콜 도구 모음"
  - "메일[C++]"
  - "메일[C++], 프로그래밍"
  - "레코드 기반 데이터[C++]"
  - "순서가 지정된 데이터 흐름"
  - "SOCKET 핸들"
  - "소켓[C++], 스트림 소켓"
  - "스트림 소켓[C++]"
  - "Windows 소켓[C++], 스트림 소켓"
  - "X Windows 서버"
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows 소켓: 백그라운드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 Windows 소켓의 특성과 목적을 설명합니다.  이 문서는 또한:  
  
-   ["소켓"이라는 용어를 정의](#_core_definition_of_a_socket).  
  
-   [소켓 핸들 데이터 형식을 설명](#_core_the_socket_data_type).  
  
-   [소켓의 용도 설명](#_core_uses_for_sockets).  
  
 Windows 소켓 사양은 Microsoft Windows 이진 호환 네트워크 프로그래밍 인터페이스를 정의합니다.  Windows 소켓은 University of California at Berkeley의 버클리 소프트웨어 배포 \(BSD, 릴리스 4.3\) 의 UNIX 소켓 구현을 기반으로 하고 있습니다.  사양은 BSD 스타일 소켓 루틴과 Windows 고유의 확장을 모두 포함하고 있습니다.  Windows 소켓을 사용하여 응용 프로그램이 Windows 소켓 API를 준수하는 네트워크를 통해 통신하는 것을 허용합니다.  Win32에서는, Windows 소켓 스레드 안전을 제공합니다.  
  
 많은 네트워크 소프트웨어 업체는 전송 제어 프로토콜\/인터넷 프로토콜 \(TCP\/IP\), Xerox 네트워크 시스템 \(XNS\), Digital Equipment Corporation의 DECNet 프로토콜, Novell Corporation의 인터넷 패킷 Exchange\/Sequenced 패킹 교환 \(IPX\/SPX\) 등을 포함한 네트워크 프로콜을 통해 Windows 소켓을 지원합니다.  현재 Windows 소켓 사양은 TCP\/IP 소켓 추상화를 정의하고 있지만, 모든 네트워크 프로토콜은 고유의 Windows 소켓을 구현하는 동적 연결 라이브러리 \(DLL\)의 버전을 제공하여 Windows 소켓을 따를 수 있습니다.  Windows 소켓을 사용하여 작성된 상업 응용 프로그램의 예로는 X Windows 서버, 터미널 에뮬레이터 및 전자 메일 시스템이 있습니다.  
  
> [!NOTE]
>  Windows 소켓의 목적은 기초적인 네트워크를 추상화하여 네트워크에 대한 지식이 없이도 응용 프로그램을 소켓을 지원하는 모든 네트워크에서 구동하는 것입니다.  따라서, 이 문서는 네트워크 프로토콜에 대해 자세히 다루지 않습니다.  
  
 Microsoft 기반 클래스 라이브러리 \(MFC\)는 두 개의 클래스를 제공하여 Windows 소켓 API를 사용한 프로그래밍을 지원합니다.  이러한 클래스 중 하나인 `CSocket`은, 네트워크 통신 프로그래밍을 단순화하는 높은 수준의 추상화를 제공합니다.  
  
 Windows 소켓 사양, Windows 소켓: Microsoft Windows용 네트워크 컴퓨팅을 위한 공개 인터페이스 \(현재 버전 1.1\) 는 TCP\/IP 커뮤니티의 개인과 회사에 의해 공개 네트워킹 표준으로 개발되었으며, 자유롭게 사용할 수 있습니다.  소켓 프로그래밍 모델은 인터넷 프로토콜 제품군을 사용하여 현재 하나의 "통신 도메인"을 지원합니다.  사양은 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]에서 사용할 수 있습니다.  
  
> [!TIP]
>  소켓은 인터넷 프로토콜 제품군을 사용하기 때문에, "정보 고속도로"에서 인터넷 통신을 지원하는 응용 프로그램에게 있어 우선적인 경로입니다.  
  
##  <a name="_core_definition_of_a_socket"></a> 소켓의 정의  
 소켓은 통신 종단 지점의 통신입니다 — 개체는 Windows 소켓 응용 프로그램을 통해 데이터 패킷을 네트워크를 통해 보내거나 받습니다.  소켓은 형식을 가지고 실행 중인 프로세스와 관련될 수 있으며, 이름을 가질 수 있습니다.  현재, 소켓은 일반적으로 인터넷 프로토콜 제품군을 사용하는 동일한 "통신 도메인" 안에서만 다른 소켓과 데이터를 교환합니다.  
  
 두 종류의 소켓은 모두 양방향입니다; 동시에 양 방향으로 \(전체가 이중\) 통신할 수 있는 데이터 흐름입니다.  
  
 두 소켓 형식을 사용할 수 있습니다.  
  
-   스트림 소켓  
  
     레코드 경계 없이 데이터 흐름을 제공하는 스트림 소켓: 바이트 스트림.  스트림은 중복없이 순차적으로 정확하게 전달하는 것을 보장합니다.  
  
-   데이터그램 소켓  
  
     데이터그램 소켓은 레코드 기반 중복없이 순차적으로 정확하게 전달하는 것을 보장하지 않는 데이터 흐름을 지원합니다.  
  
 "순차적"이란 패킷이 보낸 순서대로 배달되는 것을 의미합니다. "중복없이"란 특정 패킷은 한 번만 얻을 수 있음을 의미합니다.  
  
> [!NOTE]
>  XNS 같은 일부 네트워크 프로토콜에서는 스트림은 바이트 스트림이 아닌 레코드 지향일 수 있습니다.  그러나 일반적인 TCP\/IP 프로토콜에서 스트림은 바이트 스트림입니다.  Windows 소켓은 기반 프로토콜에 독립적인 추상화 수준을 제공합니다.  
  
 이러한 형식에 대한 정보와 어떤 종류의 소켓이 어떤 상황에 사용되는지를 보려면, [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md) 및 [Windows 소켓: 데이터 그램 소켓](../mfc/windows-sockets-datagram-sockets.md)을 참조하십시오.  
  
##  <a name="_core_the_socket_data_type"></a> SOCKET 데이터 형식  
 각 MFC 소켓 개체는 Windows 소켓 개체에 대한 핸들을 캡슐화합니다.  이 핸들의 데이터 형식은 **SOCKET**입니다.  A **SOCKET** 핸들은 창의 `HWND`와 유사합니다.  MFC 소켓 클래스는 캡슐화 된 핸들에 대한 작업을 제공합니다.  
  
 **SOCKET** 데이터 형식은 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]에 자세히 설명되어 있습니다.  Windows 소켓에서 "소켓 데이터 형식 및 오류 값"을 참조하십시오.  
  
##  <a name="_core_uses_for_sockets"></a> 소켓의 용도  
 소켓은 적어도 세 가지 통신 상황에서 매우 유용합니다.  
  
-   클라이언트\/서버 모델  
  
-   메시징 응용 프로그램 같은 피어\-투\-피어 시나리오  
  
-   호출받는 응용 프로그램이 함수 호출로써 메시지를 해석하도록 함으로써 만드는 원격 프로시저 호출 \(RPC\)  
  
> [!TIP]
>  MFC 소켓을 사용하는 가장 이상적인 경우는 통신의 양쪽 끝을 모두 작성하는 경우입니다: 양쪽 끝에 MFC를 사용합니다.  비 MFC 응용 프로그램과 통신하는 경우의 관리 방법을 포함한 이 항목에 대한 자세한 내용은 [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md)를 참조하십시오.  
  
 자세한 내용은 Windows 소켓 사양을 참조하십시오: **ntohs**, **ntohl**, **htons**, **htonl**.  또한 다음 항목도 참조하십시오.  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)