---
title: "CSocket 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
dev_langs: C++
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67fa709c0f58becfa18b286ba9c84d01c4c853dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="csocket-class"></a>CSocket 클래스
파생 `CAsyncSocket`, Windows 소켓 API의 해당 캡슐화를 상속 하 고 보다 상위 수준의 추상을 나타내는 `CAsyncSocket` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|`CSocket` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSocket::Attach](#attach)|연결 된 **소켓** 에 대 한 핸들을 `CSocket` 개체입니다.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|현재 진행 중인 차단 호출을 취소 합니다.|  
|[CSocket::Create](#create)|소켓을 만듭니다.|  
|[CSocket::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CSocket` 지정 된 개체는 **소켓** 처리 합니다.|  
|[CSocket::IsBlocking](#isblocking)|차단 호출이 진행 중인지 여부를 결정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|차단 호출이 완료 되기를 기다리는 동안 보류 중인 메시지는 처리 하기 위해 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 `CSocket`클래스와 함께 사용 `CSocketFile` 및 `CArchive` 보내고 받는 데이터를 관리할 수 있습니다.  
  
 A `CSocket` 개체도 제공 차단의 동기 작업 하는 데 필수적인 `CArchive`합니다. 와 같은 기능을 차단 `Receive`, `Send`, `ReceiveFrom`, `SendTo`, 및 `Accept` (에서 상속 된 모든 `CAsyncSocket`)를 반환 하지 않는 한 `WSAEWOULDBLOCK` 에 오류가 `CSocket`합니다. 대신 이러한 함수는 작업이 완료 될 때까지 기다립니다. 오류가 발생 하 여 원래 호출 또한 끝납니다 `WSAEINTR` 경우 `CancelBlockingCall` 이러한 함수 중 하나를 차단 하는 동안 호출 됩니다.  
  
 사용 하는 `CSocket` 개체, 생성자를 호출 호출 `Create` 내부 만들려는 `SOCKET` 처리 (형식 `SOCKET`). 기본 매개 변수 `Create` 스트림 소켓을 만들 사용 하 여 소켓을 사용 하지 않는 경우에 `CArchive` 개체 대신, 데이터 그램 소켓을 만들 하거나 서버 소켓을 만들 특정 포트에 바인딩해야 하는 매개 변수를 지정할 수 있습니다. 클라이언트 소켓 사용 하 여 연결할 `Connect` 클라이언트 쪽 및 `Accept` 서버 쪽에서 합니다. 그런 다음 만듭니다는 `CSocketFile` 개체와 연결 하는 `CSocket` 개체는 `CSocketFile` 생성자입니다. 다음으로 만듭니다는 `CArchive` 보내기 위한 개체 및 필요에 따라 데이터를 수신에 대 한 다음 연결 하는 사용 하 여는 `CSocketFile` 개체는 `CArchive` 생성자입니다. 통신 완료 되 면 삭제는 `CArchive`, `CSocketFile`, 및 `CSocket` 개체입니다. `SOCKET` 데이터 형식의 문서에 설명 되어 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md)합니다.  
  
 사용 하는 경우 `CArchive` 와 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있습니다 위치 `CSocket::Receive` 루프로 실행 (여 `PumpMessages(FD_READ)`) 기다리는 중 요청 된 바이트의 양입니다. Windows 소켓 작업할 알림 당 하나의 수신 호출을 허용 하기 때문에 이것이 하지만 `CSocketFile` 및 `CSocket` 작업할 당 여러 수신 호출을 허용 합니다. 읽을 데이터가 없는 경우에 작업할을 얻게 하는 경우 응용 프로그램이 중단 됩니다. 다른 작업할 가져오지 응용 프로그램이 소켓을 통해 통신을 중지 합니다.  
  
 다음과 같이이 문제를 해결할 수 있습니다. 에 `OnReceive` 소켓 클래스, 호출의 메서드로 `CAsyncSocket::IOCtl(FIONREAD, ...)` 호출 하기 전에 `Serialize` TCP 패킷 하나의 네트워크 중간 (최대 전송 단위 크기를 초과 하는 소켓에서 읽이 예상된 데이터 메시지 클래스의 메서드 일반적으로 적어도 1096 바이트)입니다. 사용 가능한 데이터의 크기 보다 작은 경우, 모든 데이터를 받아 읽기 작업을 다시 시작 될 때까지 기다립니다.  
  
 다음 예에서 `m_dwExpected` 사용자를 수신 해야 하는 바이트의 대략적인 수입니다. 선언 하 고 다른 곳에서 코드에 가정 됩니다.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  정적으로 연결 된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓을 사용 하 여 소켓 라이브러리를 초기화 하는 각 스레드에 있습니다. 기본적으로 `AfxSocketInit` 기본 스레드에서만에서 호출 됩니다.  
  
 자세한 내용은 참조 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows 소켓: 아카이브 작업을 사용 하는 소켓 어떻게](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows 소켓: 작업 순서](../../mfc/windows-sockets-sequence-of-operations.md), [Windows 소켓: 아카이브를 사용 하는 소켓의 예](../../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsock.h  
  
##  <a name="attach"></a>CSocket::Attach  
 연결 하려면이 함수를 호출는 `hSocket` 에 대 한 핸들을 `CSocket` 개체입니다.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하는 경우 0이 아닙니다.  
  
### <a name="remarks"></a>설명  
 **소켓** 핸들 개체의에 저장 된 [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) 데이터 멤버입니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 현재 진행 중인 차단 호출을 취소 하려면이 함수를 호출 합니다.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>설명  
 이 함수는이 소켓에 대 한 모든 미해결 차단 작업을 취소합니다. 원래 차단 호출 오류와 가능한 한 빨리 끝납니다 **WSAEINTR**합니다.  
  
 차단 하는 경우 **연결** 작업, Windows 소켓을 종료 차단 호출 가능한 하지만 불가능할 수도 있습니다는 연결이 완료 될 때까지 해제 될 소켓 리소스에 대 한 즉시 (및 다시 설정 된) 또는 시간 초과 합니다. 이 응용 프로그램에는 즉시 새 소켓 (사용할 수 없는 소켓 경우), 열 또는 동일한 피어에 연결 하려고 하는 경우에 뚜렷하게 나타날 수 있습니다.  
  
 이외의 다른 모든 작업 취소 **Accept** 소켓 비활성화 된 상태로 둘 수 있습니다. 응용 프로그램 소켓에서 수행할 수 있는 것에 종속 될 수 있는 유일한 작업에 대 한 호출은 응용 프로그램가 소켓에서 차단 작업을 취소 **닫기**다른 작업은 일부 Windows 소켓에서는 작동할 수 있지만, 구현 합니다. 응용 프로그램에 대 한 최대 이식성을 원할 경우가 취소 한 후 작업 수행에 의존 하지 않도록 주의 해야 합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="create"></a>CSocket::Create  
 호출 된 **만들기** Windows 소켓을 만들를 연결 하는 소켓 개체를 생성 한 후 멤버 함수입니다.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSocketPort`  
 MFC 포트를 선택 하려는 경우에 소켓 또는 0 함께 사용 되는 특정 포트입니다.  
  
 `nSocketType`  
 **SOCK_STREAM** 또는 **SOCK_DGRAM**합니다.  
  
 `lpszSocketAddress`  
 "128.56.22.8"과 같은 점으로 구분 된 숫자를 연결된 된 소켓의 네트워크 주소를 포함 하는 문자열에 대 한 포인터입니다. 전달는 **NULL** 문자열을이 매개 변수 나타냅니다는 **CSocket** 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 0이 고, 특정 오류 코드를 호출 하 여 검색할 수 있습니다 그렇지 않으면 `GetLastError`합니다.  
  
### <a name="remarks"></a>설명  
 **만들** 다음 호출 **바인딩할** 소켓을 바인딩하지 지정된 된 주소에 있습니다. 다음 소켓 유형이 지원 됩니다.  
  
- **SOCK_STREAM** 신뢰할 수 있는 양방향 연결 기반 바이트 스트림의 시퀀싱를 제공 합니다. 인터넷 주소 패밀리에 대 한 프로토콜 TCP (Transmission Control)를 사용합니다.  
  
- **SOCK_DGRAM** (일반적으로 짧지만) 최대 길이가 고정 연결 없는, 신뢰할 수 없는 버퍼 인 데이터 그램을 지원 합니다. 인터넷 주소 패밀리에 대해 사용자 데이터 그램 프로토콜 (UDP)을 사용합니다. 이 옵션을 사용 하려면 사용 하면 안 된 소켓은 `CArchive` 개체입니다.  
  
    > [!NOTE]
    >  **Accept** 멤버 함수는 비어 있는 새에 대 한 참조를 사용 `CSocket` 개체를 매개 변수로 합니다. 호출 하기 전에이 개체를 생성 해야 **Accept**합니다. 한다는 점에 유의 하는이 소켓 개체가 범위의 연결 닫기 외부로 이동 하는 경우. 호출 하지 마십시오 **만들기** 이 새 소켓 개체에 대 한 합니다.  
  
 스트림 및 데이터 그램 소켓에 대 한 자세한 내용은 문서를 참조 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md), [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md), 및 [Windows 소켓:를 사용 하 여 아카이브를 함께 사용 하는 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="csocket"></a>CSocket::CSocket  
 `CSocket` 개체를 생성합니다.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>설명  
 생성 후의 **만들기** 멤버 함수입니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="fromhandle"></a>CSocket::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CSocket` 개체입니다.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CSocket` 개체 또는 **NULL** 없는 경우 없는 `CSocket` 개체에 연결 되어 `hSocket`합니다.  
  
### <a name="remarks"></a>설명  
 지정 된 경우는 **소켓** 경우 처리는 `CSocket` 멤버 함수가 반환 개체가 핸들에 연결 되지 않은, **NULL** 임시 개체를 만들지 않습니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="isblocking"></a>CSocket::IsBlocking  
 차단 호출이 진행에서 중인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>반환 값  
 소켓 작업이 차단 되; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="onmessagepending"></a>CSocket::OnMessagePending  
 Windows에서 특정 메시지를 검색 하 고 프로그램 소켓에 응답할 수를이 멤버 함수를 재정의 합니다.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>반환 값  
 메시지가 처리 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 고급 재정의할 수 있습니다.  
  
 프레임 워크를 호출 하 여 `OnMessagePending` 소켓은 응용 프로그램에 관심 있는 메시지를 처리 하는 기회를 제공 하려면 Windows 메시지를 펌프 하는 동안 합니다. 사용 하는 방법에 대 한 예제 `OnMessagePending`, 문서를 참조 [Windows 소켓: 소켓 클래스에서 파생](../../mfc/windows-sockets-deriving-from-socket-classes.md)합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)
