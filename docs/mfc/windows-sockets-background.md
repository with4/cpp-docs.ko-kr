---
title: 'Windows 소켓: 백그라운드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fda86bbbeb49bcb253348ed02abef4fb8d4cff9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384939"
---
# <a name="windows-sockets-background"></a>Windows 소켓: 백그라운드
이 문서와 Windows 소켓의 목적을 설명합니다. 문서도 합니다.  
  
-   ["소켓" 라는 용어를 정의](#_core_definition_of_a_socket)합니다.  
  
-   [소켓 핸들이 데이터 형식을 설명](#_core_the_socket_data_type)합니다.  
  
-   [소켓에 대 한 용도 설명](#_core_uses_for_sockets)합니다.  
  
 Windows 소켓 사양을 Microsoft windows 이진 호환 네트워크 프로그래밍 인터페이스를 정의합니다. Windows 소켓 기반 Berkeley Software Distribution에 있는 UNIX 소켓 구현으로 (BSD, 4.3 릴리스) Berkeley에 University of California에서 합니다. 사양에는 스타일 BSD 소켓 루틴 및 Windows 관련 확장 모두 포함 됩니다. Windows 소켓을 사용 하 여 응용 프로그램 Windows 소켓 API에 맞는 모든 네트워크를 통해 통신을 허용 합니다. Win32, Windows 소켓 스레드 안전을 제공 합니다.  
  
 많은 네트워크 소프트웨어 공급 업체 Protocol/Internet Protocol TCP/IP (Transmission Control), Xerox 네트워크 시스템 (XNS) 디지털 장비 Corporation DECNet 프로토콜, Novell 회사의 인터넷을 비롯 한 네트워크 프로토콜에서 Windows 소켓 지원 패킷 교환/Sequenced 압축 된 교환 (IPX/SPX)를 사용 합니다. TCP/IP에 대 한 소켓 추상화를 정의 하는 현재 Windows 소켓 사양, 있지만 모든 네트워크 프로토콜 고유한 버전의 Windows 소켓을 구현 하는 동적 연결 라이브러리 (DLL)를 제공 하 여 Windows 소켓 따를 수 있습니다. Windows 소켓으로 작성 하는 상업용 응용 프로그램의 예로 X Windows 서버, 터미널 에뮬레이터 및 전자 메일 시스템을 들 수 있습니다.  
  
> [!NOTE]
>  Windows 소켓의 목적은 응용 프로그램이 소켓을 지 원하는 모든 네트워크에서 실행 될 수 있도록 하는 고에 있는 해당 네트워크에 대 한 지식이 없는 기본 네트워크 추상화입니다. 따라서이 설명서는 네트워크 프로토콜에 자세히 설명 하지 않습니다.  
  
 Microsoft Foundation 클래스 라이브러리 (MFC)는 두 개의 클래스를 제공 하 여 Windows 소켓 API를 사용 하 여 프로그래밍을 지원 합니다. 이러한 클래스 중 하나 `CSocket`, 높은 수준의 네트워크 통신 프로그래밍을 단순화 하는 추상화를 제공 합니다.  
  
 Windows 소켓 사양 Windows 소켓: 네트워크 컴퓨팅에서 Microsoft windows의 버전 1.1에서 이제는 열고 인터페이스가 대규모 그룹의 개인 및 회사 TCP/IP 커뮤니티에서 개발한 개방형 네트워킹 표준 고 사용 하기 위해 자유롭게 사용할 수 있습니다. 현재 모델에서는 하나의 "통신"도메인 프로그래밍, 인터넷 프로토콜 도구 모음을 사용 하 여 소켓을 사용 합니다. 사양 Windows SDK에서 제공 됩니다.  
  
> [!TIP]
>  "정보 고속도로."에 대해 인터넷 통신을 지 원하는 응용 프로그램에 대 한 기본 경로 소켓 인터넷 프로토콜 도구 모음을 사용 하므로  
  
##  <a name="_core_definition_of_a_socket"></a> 소켓 정의  
 소켓은 통신 끝점-를 통해 Windows 소켓 응용 프로그램을 보내거나 받는 데이터의 패킷을 네트워크를 통해 개체입니다. 소켓에 형식이 있고 실행 중인 프로세스에 연결 하 고 이름이 있을 수 있습니다. 현재, 소켓은 일반적으로 동일한 "통신 도메인에서" 인터넷 프로토콜 도구 모음을 사용 하 여 다른 소켓에만 데이터를 교환 합니다.  
  
 두 종류의 소켓은 양방향입니다. 양방향으로 동시에 통신할 수 있는 데이터 흐름 (양방향).  
  
 두 개의 소켓 형식을 사용할 수 있습니다.  
  
-   스트림 소켓  
  
     레코드 경계 없이 데이터 흐름에 대 한 제공 된 스트림 소켓: 바이트 스트림입니다. 배달 올바르게 순차적이 고 중복 수를 보장 됩니다.  
  
-   데이터 그램 소켓  
  
     배달 보장 되지 않으며으로 시퀀스 할 수 있습니다 하는 데이터 그램 소켓 지원 레코드 기반 데이터 흐름 순차적이 지 않거나 합니다.  
  
 "Sequenced" 의미 패킷이 보낸 순서 대로 배달 됩니다. "중복" 특정 패킷을 한 번만 가져올 의미 합니다.  
  
> [!NOTE]
>  XNS, 같은 일부 네트워크 프로토콜에서 스트림 바이트 스트림을 아닌 개의 레코드 스트림을 지향 레코드가 될 수 있습니다. 그러나 일반적인 TCP/IP 프로토콜에서 스트림을 바이트 스트림의 됩니다. Windows 소켓 기본 프로토콜의 독립적인 추상화 수준을 제공합니다.  
  
 이러한 형식에 대 한 정보에 대 한 소켓, 사용 하 여 어떤 상황에서 참조의 종류 및 [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md) 및 [Windows 소켓: 데이터 그램 소켓](../mfc/windows-sockets-datagram-sockets.md)합니다.  
  
##  <a name="_core_the_socket_data_type"></a> 소켓 데이터 형식  
 각 MFC 소켓 개체 Windows 소켓 개체에 대 한 핸들을 캡슐화합니다. 이 핸들의 데이터 형식이 **소켓**합니다. A **소켓** 핸들은 비슷합니다는 `HWND` 창에 대 한 합니다. MFC 소켓 클래스는 캡슐화 된 핸들에 대 한 작업을 제공합니다.  
  
 **소켓** 데이터 형식은 Windows SDK에서 자세히 설명 되어 있습니다. Windows 소켓에서 "소켓 데이터 형식과 오류 값"을 참조 하십시오.  
  
##  <a name="_core_uses_for_sockets"></a> 소켓의 용도  
 소켓은 세 개 이상의 통신 상황에서 매우 유용 합니다.  
  
-   클라이언트/서버 모델입니다.  
  
-   메시징 응용 프로그램 등의 피어 투 피어 시나리오  
  
-   수신 응용 프로그램은 함수 호출으로 메시지를 해석 하 여 원격 프로시저 호출 (RPC) 만들기  
  
> [!TIP]
>  MFC 소켓을 사용 하기 위한 이상적인 사례는 통신의 양쪽 끝을 작성 하는 경우: 양쪽 끝에서 MFC를 사용 합니다. 비 MFC 응용 프로그램과 통신 하는 경우 대/소문자를 관리 하는 방법을 비롯 하 여이 항목에 대 한 자세한 내용은 참조 [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)합니다.  
  
 자세한 내용은 Windows Sockets 사양을 참조: **ntohs**, **ntohl**, **htons**, **htonl**합니다. 또한 다음 항목을 참조 합니다.  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

