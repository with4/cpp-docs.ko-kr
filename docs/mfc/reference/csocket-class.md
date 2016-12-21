---
title: "CSocket Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocket class"
  - "SOCKET handle"
  - "sockets classes"
  - "WinSock CSocket class"
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파생 된 `CAsyncSocket`상속 Windows 소켓 api를 캡슐화 하 고 보다 더 높은 수준의 추상화를 나타내는 한 `CAsyncSocket` 개체.  
  
## 구문  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CSocket::CSocket](../Topic/CSocket::CSocket.md)|`CSocket` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSocket::Attach](../Topic/CSocket::Attach.md)|첨부 한  **소켓** 핸들은 `CSocket` 개체입니다.|  
|[CSocket::CancelBlockingCall](../Topic/CSocket::CancelBlockingCall.md)|현재 진행 중인 블로킹 호출을 취소 합니다.|  
|[CSocket::Create](../Topic/CSocket::Create.md)|소켓을 만듭니다.|  
|[CSocket::FromHandle](../Topic/CSocket::FromHandle.md)|에 대 한 포인터를 반환 된 `CSocket` 지정 하는 개체는  **소켓** 처리.|  
|[CSocket::IsBlocking](../Topic/CSocket::IsBlocking.md)|블로킹 호출이 진행 중인지 여부를 확인 합니다.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSocket::OnMessagePending](../Topic/CSocket::OnMessagePending.md)|메시지 보류 프로세스 완료 하려면 차단 호출을 기다리는 동안 호출.|  
  
## 설명  
 `CSocket`클래스와 함께 작동 `CSocketFile` 및 `CArchive` 를 보내고 데이터를 관리할 수 있습니다.  
  
 A `CSocket` 개체를 제공 하면 차단이 동기 작동에 필수적입니다 `CArchive`.  Blocking functions, such as `Receive`, `Send`, `ReceiveFrom`, `SendTo`, and `Accept` \(all inherited from `CAsyncSocket`\), do not return a `WSAEWOULDBLOCK` error in `CSocket`.  대신, 작업이 완료 될 때까지 이러한 함수를 기다립니다.  원래 호출 오류와 함께 종료 됩니다 또한 `WSAEINTR` 경우 `CancelBlockingCall` 이러한 함수 중 하나를 차단 하는 동안 호출 됩니다.  
  
 사용 하는 `CSocket` 개체를 생성자를 호출한 다음 호출 `Create` 내부를 만들려면 `SOCKET` 처리 \(형식 `SOCKET`\).  기본 매개 변수를 `Create` 는 스트림 소켓을 만들지 않지만 소켓을 사용 하는 경우는 `CArchive` 개체 대신 데이터 그램 소켓을 만들 또는 특정 포트에 서버 소켓을 만들기 위해 바인딩할 매개 변수를 지정할 수 있습니다.  사용 하 여 클라이언트 소켓 연결 `Connect` 클라이언트 쪽 및 `Accept` 서버 쪽.  다음 만들는 `CSocketFile` 개체와 연결 하는 `CSocket` 개체의 `CSocketFile` 생성자입니다.  만든 다음에 `CArchive` 보내기에 대해 개체 및 필요에 따라 데이터를 받기 위해 한 다음 연결 된는 `CSocketFile` 개체의 `CArchive` 생성자.  통신 완료 되 면, 파괴는 `CArchive`, `CSocketFile`, 및 `CSocket` 개체입니다.  `SOCKET` 데이터 형식이 설명 되어 문서에서  [Windows 소켓: 배경](../../mfc/windows-sockets-background.md).  
  
 사용 하는 경우 `CArchive` 와 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있습니다 위치 `CSocket::Receive` 는 루프를 입력 \(여 `PumpMessages(FD_READ)`\) 바이트 요청 된 시간 동안 대기.  Windows 소켓 마스킹해야 알림 당 하나의 recv 호출을 허용 하기 때문입니다 하지만 `CSocketFile` 및 `CSocket` 마스킹해야 당 여러 recv 호출을 허용 합니다.  읽을 데이터가 없는 경우를 마스킹해야 표시 되 면 응용 프로그램이 정지 합니다.  다른 마스킹해야 되지 않으면 소켓을 통해 통신 응용 프로그램을 중지 합니다.  
  
 다음과 같은 방법으로이 문제를 해결할 수 있습니다.  에 `OnReceive` 메서드를 호출 하 여 소켓 클래스의 `CAsyncSocket::IOCtl(FIONREAD, ...)` 를 호출 하기 전에 `Serialize` 소켓에서 읽을 수 있도록 예상된 데이터 하나의 TCP 패킷 \(일반적으로 최소한 1096 바이트 네트워크 미디어의 최대 전송 단위\) 크기를 초과 하면 메시지 클래스의 메서드를.  사용할 수 있는 데이터의 크기 보다 작은 경우 받을 수 및 경우에 읽기 작업을 시작 하려면 모든 데이터를 기다립니다.  
  
 다음 예제에서 `m_dwExpected` 의 대략적인 개수 사용자 나타날 것으로 예상 되는 바이트 수입니다.  다른 곳에서 코드에서 선언할 것으로 간주 됩니다.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/CPP/csocket-class_1.cpp)]  
  
> [!NOTE]
>  보조 스레드에서 정적으로 링크 된 MFC 응용 프로그램에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 각 스레드에서 소켓을 사용 하 여 소켓 라이브러리를 초기화할 수 있습니다.  기본적으로 `AfxSocketInit` 에서 주 스레드에서만 호출 됩니다.  
  
 자세한 내용은  [mfc에서 Windows 소켓](../../mfc/windows-sockets-in-mfc.md),  [Windows 소켓: 보관 파일을 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md),  [Windows 소켓: 소켓 보관 작업을 얼마나](../../mfc/windows-sockets-how-sockets-with-archives-work.md),  [Windows 소켓: 작업의 순서](../../mfc/windows-sockets-sequence-of-operations.md),  [Windows 소켓: 소켓을 사용 하 여 보관 파일 예제](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## 요구 사항  
 **헤더:** afxsock.h  
  
## 참고 항목  
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)