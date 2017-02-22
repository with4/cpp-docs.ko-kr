---
title: "CAsyncSocket Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous Windows Sockets"
  - "CAsyncSocket class"
  - "통신[C++], 네트워크"
  - "network communications"
  - "sockets [C++], Windows"
  - "Windows Sockets [C++], 비동기"
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAsyncSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 소켓을 나타내는\-네트워크 통신의 끝점입니다.  
  
## 구문  
  
```  
class CAsyncSocket : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAsyncSocket::CAsyncSocket](../Topic/CAsyncSocket::CAsyncSocket.md)|`CAsyncSocket` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md)|소켓 연결을 수락합니다.|  
|[CAsyncSocket::AsyncSelect](../Topic/CAsyncSocket::AsyncSelect.md)|이벤트 알림 소켓을 요청 합니다.|  
|[CAsyncSocket::Attach](../Topic/CAsyncSocket::Attach.md)|소켓 핸들을 첨부 한 `CAsyncSocket` 개체입니다.|  
|[CAsyncSocket::Bind](../Topic/CAsyncSocket::Bind.md)|로컬 주소를 소켓에 연결합니다.|  
|[CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)|소켓을 닫습니다.|  
|[CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md)|피어 소켓에 연결 합니다.|  
|[CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)|소켓을 만듭니다.|  
|[CAsyncSocket::Detach](../Topic/CAsyncSocket::Detach.md)|소켓 핸들에서 분리 된 `CAsyncSocket` 개체입니다.|  
|[CAsyncSocket::FromHandle](../Topic/CAsyncSocket::FromHandle.md)|반환에 대 한 포인터는 `CAsyncSocket` 소켓 핸들을 지정 하는 개체를 합니다.|  
|[CAsyncSocket::GetLastError](../Topic/CAsyncSocket::GetLastError.md)|실패 한 마지막 작업에 대 한 오류 상태를 가져옵니다.|  
|[CAsyncSocket::GetPeerName](../Topic/CAsyncSocket::GetPeerName.md)|피어 연결 된 소켓에 소켓의 주소를 가져옵니다.|  
|[CAsyncSocket::GetPeerNameEx](../Topic/CAsyncSocket::GetPeerNameEx.md)|피어 연결된 \(핸들 IPv6 주소\)는 소켓에 소켓의 주소를 가져옵니다.|  
|[CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md)|소켓의 로컬 이름을 가져옵니다.|  
|[CAsyncSocket::GetSockNameEx](../Topic/CAsyncSocket::GetSockNameEx.md)|소켓 \(i p v 6 주소 핸들\)에 대 한 로컬 이름을 가져옵니다.|  
|[CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)|소켓 옵션을 검색합니다.|  
|[CAsyncSocket::IOCtl](../Topic/CAsyncSocket::IOCtl.md)|소켓의 모드를 제어합니다.|  
|[CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)|들어오는 연결 요청을 수신 대기 소켓을 설정 합니다.|  
|[CAsyncSocket::Receive](../Topic/CAsyncSocket::Receive.md)|소켓에서 데이터를 받습니다.|  
|[CAsyncSocket::ReceiveFrom](../Topic/CAsyncSocket::ReceiveFrom.md)|데이터 그램을 받고 소스 주소를 저장 합니다.|  
|[CAsyncSocket::ReceiveFromEx](../Topic/CAsyncSocket::ReceiveFromEx.md)|데이터 그램을 받고 소스 주소 \(IPv6 주소 핸들\)를 저장 합니다.|  
|[CAsyncSocket::Send](../Topic/CAsyncSocket::Send.md)|연결 된 소켓에 데이터를 보냅니다.|  
|[CAsyncSocket::SendTo](../Topic/CAsyncSocket::SendTo.md)|특정 대상에 데이터를 보냅니다.|  
|[CAsyncSocket::SendToEx](../Topic/CAsyncSocket::SendToEx.md)|\(핸들 IPv6 주소\)를 특정 대상에 데이터를 보냅니다.|  
|[CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)|소켓 옵션을 설정합니다.|  
|[CAsyncSocket::ShutDown](../Topic/CAsyncSocket::ShutDown.md)|해제  **보내기** 및\/또는  **수신** 소켓에 호출 합니다.|  
|[CASyncSocket::Socket](../Topic/CASyncSocket::Socket.md)|소켓 핸들을 할당 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAsyncSocket::OnAccept](../Topic/CAsyncSocket::OnAccept.md)|호출 하 여 보류 중인 연결 요청을 수락 하는 수신 대기 소켓을 알리는  **수락**.|  
|[CAsyncSocket::OnClose](../Topic/CAsyncSocket::OnClose.md)|소켓에 연결 된 소켓을 닫았습니다 알립니다.|  
|[CAsyncSocket::OnConnect](../Topic/CAsyncSocket::OnConnect.md)|연결 소켓 연결 시도 여부 오류 또는 성공적으로 완료 되는 알립니다.|  
|[CAsyncSocket::OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md)|소켓 수신 대역의 데이터를 소켓에 긴급 메시지 일반적으로 있는지 알립니다.|  
|[CAsyncSocket::OnReceive](../Topic/CAsyncSocket::OnReceive.md)|수신 대기 소켓을 호출 하 여 검색할 수 있습니다 알립니다  **수신**.|  
|[CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)|소켓 호출 하 여 데이터 전송할 수 있음을 알리는  **보내기**.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAsyncSocket::operator \=](../Topic/CAsyncSocket::operator%20=.md)|새 값에 지정 된 `CAsyncSocket` 개체.|  
|[CAsyncSocket::operator SOCKET](../Topic/CAsyncSocket::operator%20SOCKET.md)|이 연산자를 사용 하 여 검색 하는  **소켓** 의 처리는 `CAsyncSocket` 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAsyncSocket::m\_hSocket](../Topic/CAsyncSocket::m_hSocket.md)|표시는  **소켓** 핸들을 연결 하려면 `CAsyncSocket` 개체.|  
  
## 설명  
 클래스 `CAsyncSocket` 와 함께 MFC Windows 소켓을 사용 하려는 프로그래머에 게 개체 지향적 추상화를 제공 하는 Windows 소켓 함수 API를 캡슐화 합니다.  
  
 이 클래스는 네트워크 통신을 이해 하는 가정에 기반으로 합니다.  차단, 바이트 순서 차이 처리 하기 위해 담당 및 변환 유니코드와 멀티 바이트 문자 \(MBCS\) 문자열을 설정 합니다.  이러한 문제를 관리 하는 편리한 인터페이스를 원하는 경우 클래스를 참조 하십시오.  [CSocket](../../mfc/reference/csocket-class.md).  
  
 사용 하는 `CAsyncSocket` 개체, 해당 생성자를 호출 다음 호출의  [만들기](../Topic/CAsyncSocket::Create.md) 내부 소켓 핸들을 만드는 기능 \(형식 `SOCKET`\)를 받아들인된 소켓을 제외 하 고.  서버 소켓 호출에 대 한의  [수신](../Topic/CAsyncSocket::Listen.md) 멤버 함수 및 클라이언트 소켓 호출에는  [연결](../Topic/CAsyncSocket::Connect.md) 멤버 함수.  서버 소켓 호출을  [수락](../Topic/CAsyncSocket::Accept.md) 연결 요청을 수신 하는 함수.  나머지 사용 `CAsyncSocket` 소켓 간의 통신을 수행 하는 함수입니다.  완료 되 면 파괴 된 `CAsyncSocket` 개체는 힙에; 만들어졌으면 자동으로 소멸자를 호출 하는  [닫기](../Topic/CAsyncSocket::Close.md) 함수입니다.  `SOCKET` 데이터 형식 문서에 설명 된  [Windows 소켓: 배경](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  보조 스레드에서 정적으로 링크 된 MFC 응용 프로그램에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 각 스레드에서 소켓을 사용 하 여 소켓 라이브러리를 초기화할 수 있습니다.  기본적으로 `AfxSocketInit` 주 스레드에서만 호출 됩니다.  
  
 자세한 내용은  [Windows 소켓: 클래스 CAsyncSocket 사용 하 여](../../mfc/windows-sockets-using-class-casyncsocket.md) 및 관련 기사.과  [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## 요구 사항  
 **헤더:**  afxsock.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)