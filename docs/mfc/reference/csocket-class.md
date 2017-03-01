---
title: "CSocket 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocket
dev_langs:
- C++
helpviewer_keywords:
- WinSock CSocket class
- CSocket class
- SOCKET handle
- sockets classes
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 451ea100dbf02e365204fe4fdf1c380e855d8231
ms.lasthandoff: 02/24/2017

---
# <a name="csocket-class"></a>CSocket 클래스
파생 되며 `CAsyncSocket`, Windows 소켓 API의 해당 캡슐화를 상속 하며 보다 높은 수준의 추상화를 나타내는 `CAsyncSocket` 개체입니다.  
  
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
|[CSocket::Attach](#attach)|연결을 **소켓** 에 대 한 핸들을 `CSocket` 개체입니다.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|현재 진행 중인 차단 호출을 취소 합니다.|  
|[CSocket::Create](#create)|소켓을 만듭니다.|  
|[CSocket::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CSocket` 지정 된 개체는 **소켓** 처리 합니다.|  
|[CSocket::IsBlocking](#isblocking)|차단 호출 진행 중인지 여부를 결정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|차단 호출이 끝나기를 기다리는 동안 보류 된 메시지는 처리 하기 위해 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 `CSocket`클래스와 함께 사용 `CSocketFile` 및 `CArchive` 를 보내고 받는 데이터를 관리할 수 있습니다.  
  
 A `CSocket` 개체에는 차단의 동기 작업 하는 데 필수적인 `CArchive`합니다. 와 같은 기능을 차단 `Receive`, `Send`, `ReceiveFrom`, `SendTo`, 및 `Accept` (에서 상속 되는 모든 `CAsyncSocket`)을 반환 하지 않는 `WSAEWOULDBLOCK` 에 오류가 `CSocket`합니다. 대신 이러한 함수는 작업이 완료 될 때까지 기다립니다. 오류가 발생 하 여 원래 호출 끝납니다 또한 `WSAEINTR` 경우 `CancelBlockingCall` 이러한 함수 중 하나를 차단 하는 동안 호출 됩니다.  
  
 사용 하는 `CSocket` 개체, 생성자를 호출 다음 호출 `Create` 내부 만들려는 `SOCKET` 처리 (형식 `SOCKET`). 기본 매개 변수 `Create` 는 스트림 소켓을 만들기와 소켓을 사용 하지 않는 경우에 `CArchive` 개체 대신 데이터 그램 소켓 만들거나 서버 소켓을 만들지 특정 포트에 바인딩 매개 변수를 지정할 수 있습니다. 사용 하 여 클라이언트 소켓에 연결 `Connect` 클라이언트 쪽 및 `Accept` 서버 쪽입니다. 다음 만듭니다는 `CSocketFile` 개체와 연결 하는 `CSocket` 개체는 `CSocketFile` 생성자입니다. 다음으로 만듭니다는 `CArchive` 보내기에 대 한 개체 및 필요에 따라 데이터를 수신 하는 것에 대 한 다음 연결 하는 사용 하 여는 `CSocketFile` 개체는 `CArchive` 생성자입니다. 통신 완료 되 면 삭제는 `CArchive`, `CSocketFile`, 및 `CSocket` 개체입니다. `SOCKET` 데이터 형식의 문서에 설명 되어 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md)합니다.  
  
 사용 하는 경우 `CArchive` 와 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있습니다 여기서 `CSocket::Receive` 루프로 실행 (여 `PumpMessages(FD_READ)`) 요청된 된 양의 바이트에 대 한 대기 합니다. 이 Windows 소켓 작업할 알림 당 하나의 recv 호출만 허용 하지만 `CSocketFile` 및 `CSocket` 작업할 당 여러 recv 호출을 허용 합니다. 읽을 데이터가 없을 때에 작업할을 받게 되 면 응용 프로그램이 중단 됩니다. 다른 작업할 만들기란 응용 프로그램이 소켓을 통해 통신을 중지 합니다.  
  
 다음과 같이이 문제를 해결할 수 있습니다. 에 `OnReceive` socket 클래스, 호출의 메서드로 `CAsyncSocket::IOCtl(FIONREAD, ...)` 호출 하기 전에 `Serialize` 소켓에서 읽이 예상된 데이터 TCP 패킷 하나의 (네트워크 매체에 일반적으로 1096 바이트 이상 최대 전송 단위)의 크기를 초과 하는 경우 메시지 클래스의 메서드. 사용 가능한 데이터의 크기 보다 작은 경우, 모든 데이터를 받고 다음 읽기 작업을 시작 될 때까지 기다립니다.  
  
 다음 예에서 `m_dwExpected` 를 받는 사용자가 기대 하는 바이트의 대략적인 수입니다. 선언 하면 다른 곳에서 코드에 가정 됩니다.  
  
 [!code-cpp[NVC_MFCSocketThread #&4;](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  보조 스레드는 정적으로 연결 된 MFC 응용 프로그램에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓 라이브러리를 초기화할 수 소켓을 사용 하 여 각 스레드에서 합니다. 기본적으로 `AfxSocketInit` 기본 스레드에만 호출 됩니다.  
  
 자세한 내용은 참조 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows 소켓: 아카이브 작업을 사용 하는 소켓 어떻게](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows 소켓: 작업 순서](../../mfc/windows-sockets-sequence-of-operations.md), [Windows 소켓: 소켓을 사용 하 여 보관 파일 예제](../../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsock.h  
  
##  <a name="a-nameattacha--csocketattach"></a><a name="attach"></a>CSocket::Attach  
 연결 하려면이 멤버 함수를 호출 하는 `hSocket` 에 대 한 핸들을 `CSocket` 개체.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하는 경우&0;이 아닙니다.  
  
### <a name="remarks"></a>주의  
 **소켓** 핸들 개체에 저장 됩니다 [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) 데이터 멤버입니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCSocketThread #&1;](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread #&2;](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread #&3;](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="a-namecancelblockingcalla--csocketcancelblockingcall"></a><a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 진행 중인 블로킹 호출을 취소 하려면이 멤버 함수를 호출 합니다.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>주의  
 이 함수는이 소켓에 대 한 모든 미해결 차단 작업을 취소합니다. 원래 차단 호출 오류와 가능한 한 빨리 끝납니다 **WSAEINTR**합니다.  
  
 차단의 경우 **연결** 작업의 경우 Windows 소켓 구현이 끝납니다 차단 호출 가능한 만들었지만 하지 못할 때까지 연결에 완료 (다음 다시 설정 되었습니다) 출시 될 소켓 리소스에 대 한 즉시 또는 시간 초과 합니다. 이 응용 프로그램에는 즉시 새 소켓 (사용할 수 없는 소켓 경우)를 열거나 같은 피어에 연결 하려고 하는 경우에 뚜렷하게 나타날 수 있습니다.  
  
 이외의 다른 모든 작업을 취소 **Accept** 소켓 확정 상태로 둘 수 있습니다. 소켓에서 차단 작업을 취소 하는 응용 프로그램을 응용 프로그램에서 소켓을 수행할 수 있는 것에 참조할 수 있는 유일한 작업 인지에 대 한 호출 **닫기**일부 Windows 소켓 구현에서 다른 작업이 실행 될 수도 있지만, 합니다. 응용 프로그램에 대 한 최대 이식성을 원하는 경우 취소 한 후 작업 수행에 종속 되지 않도록 주의 해야 합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="a-namecreatea--csocketcreate"></a><a name="create"></a>CSocket::Create  
 호출 된 **만들기** Windows 소켓을 만들고 연결 하는 소켓 개체를 생성 한 후 멤버 함수입니다.  
  
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
 "128.56.22.8" 등의 점으로 구분 된 숫자를 연결된 된 소켓의 네트워크 주소를 포함 하는 문자열에 대 한 포인터입니다. 전달 된 **NULL** 이 매개 변수를 나타내는 문자열는 **CSocket** 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 `GetLastError`합니다.  
  
### <a name="remarks"></a>주의  
 **만들** 다음 호출 **바인딩할** 소켓을 바인딩하지 지정된 된 주소에 있습니다. 다음과 같은 소켓 유형이 지원 됩니다.  
  
- **SOCK_STREAM** 신뢰할 수 있는 양방향 연결 기반 바이트 스트림의 시퀀스를 제공 합니다. 인터넷 주소 패밀리에 대해 전송 제어 프로토콜 (TCP)을 사용합니다.  
  
- **SOCK_DGRAM** 는 최대 길이가 고정된 (일반적으로 작은)의 연결 없는, 안정적이 지 않은 버퍼는 데이터 그램을 지원 합니다. 인터넷 주소 패밀리에 대해 사용자 데이터 그램 프로토콜 (UDP)을 사용합니다. 이 옵션을 사용 하려면 사용 하면 안 된 소켓을 `CArchive` 개체입니다.  
  
    > [!NOTE]
    >  **Accept** 멤버 함수는 비어 있는 새에 대 한 참조를 사용 `CSocket` 개체를 매개 변수로 합니다. 호출 하기 전에이 개체를 생성 해야 **Accept**합니다. 사항으로이 소켓 개체가 범위를 연결이 닫힙니다 사라지면 합니다. 호출 하지 마십시오 **만들기** 이 새 소켓 개체에 대 한 합니다.  
  
 스트림 및 데이터 그램 소켓에 대 한 자세한 내용은 문서를 참조 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md), [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md), 및 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="a-namecsocketa--csocketcsocket"></a><a name="csocket"></a>CSocket::CSocket  
 `CSocket` 개체를 생성합니다.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 하는 생성 후는 **만들기** 멤버 함수입니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="a-namefromhandlea--csocketfromhandle"></a><a name="fromhandle"></a>CSocket::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CSocket` 개체입니다.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CSocket` 개체 또는 **NULL** 없을 경우 없는 `CSocket` 개체에 연결 된 `hSocket`합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 경우는 **소켓** 경우 처리는 `CSocket` 멤버 함수는 반환 된 핸들에는 개체가 연결 되지 않은, **NULL** 임시 개체를 만들지 않습니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="a-nameisblockinga--csocketisblocking"></a><a name="isblocking"></a>CSocket::IsBlocking  
 차단 호출 진행에서 중인지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>반환 값  
 소켓; 차단 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="a-nameonmessagependinga--csocketonmessagepending"></a><a name="onmessagepending"></a>CSocket::OnMessagePending  
 Windows에서 특정 메시지를 확인 하 고 프로그램 소켓에 응답할 수를이 멤버 함수를 재정의 합니다.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>반환 값  
 메시지가 처리 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 고급 재정의할 수 있습니다.  
  
 프레임 워크 호출 `OnMessagePending` 소켓은 응용 프로그램에 관심 있는 메시지를 처리 하는 기회를 제공 하려면 Windows 메시지를 펌프 하는 동안. 사용 하는 방법에 대 한 예제 `OnMessagePending`, 문서를 참조 하십시오 [Windows 소켓: 소켓 클래스에서 파생](../../mfc/windows-sockets-deriving-from-socket-classes.md)합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)

