---
title: "CAsyncSocket 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
dev_langs:
- C++
helpviewer_keywords:
- network communications
- asynchronous Windows Sockets
- CAsyncSocket class
- Windows Sockets [C++], asynchronous
- communications [C++], network
- sockets [C++], Windows
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7a175fc12146d98becc5d06f80e975df5b5a008
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="casyncsocket-class"></a>CAsyncSocket 클래스
Windows 소켓 나타냅니다 — 네트워크 통신의 끝점입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|`CAsyncSocket` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|소켓에 대 한 연결을 허용합니다.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|소켓에 대 한 요청 이벤트 알림입니다.|  
|[CAsyncSocket::Attach](#attach)|연결에 대 한 소켓 핸들을 `CAsyncSocket` 개체입니다.|  
|[CAsyncSocket::Bind](#bind)|소켓 로컬 주소에 연결합니다.|  
|[CAsyncSocket::Close](#close)|소켓을 닫습니다.|  
|[CAsyncSocket::Connect](#connect)|피어 소켓에 대 한 연결을 설정합니다.|  
|[CAsyncSocket::Create](#create)|소켓을 만듭니다.|  
|[CAsyncSocket::Detach](#detach)|소켓 핸들을 분리 한 `CAsyncSocket` 개체입니다.|  
|[CAsyncSocket::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CAsyncSocket` 소켓 핸들을 지정 된 개체입니다.|  
|[CAsyncSocket::GetLastError](#getlasterror)|실패 한 마지막 작업에 대 한 오류 상태를 가져옵니다.|  
|[CAsyncSocket::GetPeerName](#getpeername)|소켓이 연결 되어 있는 피어 소켓의 주소를 가져옵니다.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|소켓을 연결된 (핸들 IPv6 주소)는 피어 소켓의 주소를 가져옵니다.|  
|[CAsyncSocket::GetSockName](#getsockname)|소켓에 대 한 로컬 이름을 가져옵니다.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|소켓 (핸들 IPv6 주소)에 대 한 로컬 이름을 가져옵니다.|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|소켓 옵션을 검색합니다.|  
|[CAsyncSocket::IOCtl](#ioctl)|소켓의 모드를 제어 합니다.|  
|[CAsyncSocket::Listen](#listen)|들어오는 연결 요청을 수신 대기 소켓을 설정 합니다.|  
|[CAsyncSocket::Receive](#receive)|소켓에서 데이터를 수신합니다.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|데이터 그램을 수신 하 고 원본 주소를 저장 합니다.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|데이터 그램을 수신 하 고 원본 주소 (IPv6 주소 핸들)를 저장 합니다.|  
|[CAsyncSocket::Send](#send)|연결 된 소켓에 데이터를 보냅니다.|  
|[CAsyncSocket::SendTo](#sendto)|특정 대상에 데이터를 보냅니다.|  
|[CAsyncSocket::SendToEx](#sendtoex)|데이터를 특정 대상 (핸들 IPv6 주소)를 보냅니다.|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|소켓 옵션을 설정합니다.|  
|[CAsyncSocket::ShutDown](#shutdown)|사용 하지 않도록 설정 **보낼** 및/또는 **수신** 소켓에서를 호출 합니다.|  
|[CASyncSocket::Socket](#socket)|Socket 핸들을 할당합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|호출 하 여 보류 중인 연결 요청 받을 수 있는 수신 대기 소켓 알립니다 **Accept**합니다.|  
|[CAsyncSocket::OnClose](#onclose)|소켓에 연결 된 소켓을 닫에 알립니다.|  
|[CAsyncSocket::OnConnect](#onconnect)|연결 시도가 완료 되었는지 여부를 성공 또는 오류에서 소켓에 연결 하는 알립니다.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|수신 소켓 긴급 한 메시지는 일반적으로 소켓에서 읽을 수 있는 대역폭을 벗어난 데이터 중임을 알립니다.|  
|[CAsyncSocket::OnReceive](#onreceive)|호출 하 여 검색 데이터가 수신 대기 소켓 알립니다 **수신**합니다.|  
|[CAsyncSocket::OnSend](#onsend)|호출 하 여 데이터를 보낼 수는 소켓 알립니다 **보낼**합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|에 새 값을 할당 한 `CAsyncSocket` 개체입니다.|  
|[CAsyncSocket::operator 소켓](#operator_socket)|이 연산자를 사용 하 여 검색 하는 **소켓** 의 처리는 `CAsyncSocket` 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|나타냅니다는 **소켓** 이에 연결 된 핸들 `CAsyncSocket` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 클래스 `CAsyncSocket` MFC와 함께에서 Windows 소켓을 사용 하려는 프로그래머를 위한 개체 지향 추상화를 제공 하는 Windows 소켓 함수 API를 캡슐화 합니다.  
  
 이 클래스는 가정을 기반으로 네트워크 통신을 이해 해야 합니다. 차단, 바이트 순서 차이 처리 하는 것에 대 한 책임이 및 유니코드 및 멀티 바이트 문자 간의 변환 집합 (MBCS) 문자열입니다. 이러한 문제를 관리 하는 보다 편리한 인터페이스를 사용 하도록 하려는 경우 클래스를 참조 하십시오. [CSocket](../../mfc/reference/csocket-class.md)합니다.  
  
 사용 하는 `CAsyncSocket` 개체를 해당 생성자를 호출 다음 호출는 [만들기](#create) 기본 소켓 핸들을 만들 함수입니다 (형식 `SOCKET`), 수락 된 소켓을 제외 하 고 있습니다. 서버 소켓 호출에 대 한는 [수신](#listen) 멤버 함수 및 클라이언트 소켓 호출에 대해는 [연결](#connect) 멤버 함수입니다. 서버 소켓과 호출 해야는 [Accept](#accept) 연결 요청을 받으면 함수입니다. 나머지를 사용 하 여 `CAsyncSocket` 소켓 사이의 통신을 수행 하는 함수입니다. 완료 되 면 삭제는 `CAsyncSocket` 개체 힙에 만들어졌으면;는 소멸자가 자동으로 호출 하는 [닫기](#close) 함수입니다. `SOCKET` 데이터 형식의 문서에 설명 되어 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md)합니다.  
  
> [!NOTE]
>  보조 스레드는 정적으로 연결 된 MFC 응용 프로그램에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓 라이브러리를 초기화할 수 소켓을 사용 하 여 각 스레드에서 합니다. 기본적으로 `AfxSocketInit` 기본 스레드에만 호출 됩니다.  
  
 자세한 내용은 참조 [Windows 소켓: 클래스를 사용 하 여 CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) 관련 기사.로 [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 소켓 연결을 허용 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `rConnectedSocket`  
 연결에 사용할 수 있는 새 소켓을 식별 하는 참조입니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 네트워크에 알려 지는 연결의 주소를 수신 하는 구조 소켓 합니다. 정확한 형식을 `lpSockAddr` 인수는 소켓을 만들 때 설정 된 주소 패밀리에 의해 결정 됩니다. 경우 `lpSockAddr` 및/또는 `lpSockAddrLen` 과 같은 **NULL**, 반환 되 고 받아들인된 소켓의 원격 주소에 대 한 정보가 없습니다.  
  
 `lpSockAddrLen`  
 주소 길이에 대 한 포인터 `lpSockAddr` (바이트)에서입니다. `lpSockAddrLen` 는 결과 값 매개 변수: 처음 가리키는 공간의 크기를 포함 해야 `lpSockAddr`; 반환이 반환 되는 주소의 실제 길이 (바이트)에 포함 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수가 너무 작습니다 (의 크기 보다 작은 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조).  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 호출이 진행 중입니다.  
  
- **WSAEINVAL** `Listen` 적용할 호출된 전에 없습니다.  
  
- **WSAEMFILE** 큐가 비어 수락에 진입할 때와 사용할 수 있는 설명자가 없습니다.  
  
- `WSAENOBUFS`사용할 수 있는 버퍼 공간이 없습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP** 참조 된 소켓 연결 지향 서비스를 지 원하는 유형이 아닙니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시 되어 비차단 같이 연결을 허용 하기 위해 제공 하 고 있습니다.  
  
### <a name="remarks"></a>주의  
 이 루틴의 보류 중인 연결 큐에서 첫 번째 연결을 추출,이 소켓 같은 속성을 사용 하 여 새 소켓을 만듭니다 및에 연결 `rConnectedSocket`합니다. 없는 보류 중인 연결 큐에 있는 경우 **Accept**&0;을 반환 하 고 `GetLastError` 에서 오류를 반환 합니다. 받아들인된 소켓 ( *rConnectedSocket)* 더 많은 연결을 허용 하도록 사용할 수 없습니다. 원래 소켓 열려 있는 상태 수신 대기 합니다.  
  
 인수 `lpSockAddr` 통신 계층에 알려 지는 소켓에는 연결의 주소를 사용 하 여 입력 되는 결과 매개 변수입니다. **수락** 와 같은 소켓 연결 기반 형식을 사용한 **SOCK_STREAM**합니다.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 소켓에 대 한 이벤트 알림을 요청 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lEvent`  
 응용 프로그램은 관심 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.  
  
- **작업할** 읽기를 위한 준비 상태에 대 한 알림을 수신 하려면.  
  
- **FD_WRITE** 원하는 데이터를 읽을 수 있는 경우 알림을 받을 수 있습니다.  
  
- **FD_OOB** 밴드의 범위를 벗어난 데이터에 대 한 알림을 수신 하려면.  
  
- **FD_ACCEPT** 들어오는 연결에 대 한 알림을 수신 하려면.  
  
- **FD_CONNECT** 연결 결과 대 한 알림을 수신 하려면.  
  
- **FD_CLOSE** 소켓 피어에서 닫힌 때 알림을 받으려면를 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEINVAL** 잘못 되었음이 지정된 된 매개 변수 중 하나를 나타냅니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 소켓에 대 한 MFC 콜백 알림 함수를 호출할지 지정에 사용 됩니다. `AsyncSelect`이 소켓 비차단 모드 자동 설정 됩니다. 자세한 내용은 문서를 참조 하십시오. [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 연결 하려면이 멤버 함수를 호출 하는 `hSocket` 에 대 한 핸들는 `CAsyncSocket` 개체입니다.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
 `lEvent`  
 응용 프로그램은 관심 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.  
  
- **작업할** 읽기를 위한 준비 상태에 대 한 알림을 수신 하려면.  
  
- **FD_WRITE** 원하는 데이터를 읽을 수 있는 경우 알림을 받을 수 있습니다.  
  
- **FD_OOB** 밴드의 범위를 벗어난 데이터에 대 한 알림을 수신 하려면.  
  
- **FD_ACCEPT** 들어오는 연결에 대 한 알림을 수신 하려면.  
  
- **FD_CONNECT** 연결 결과 대 한 알림을 수신 하려면.  
  
- **FD_CLOSE** 소켓 피어에서 닫힌 때 알림을 받으려면를 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하는 경우&0;이 아닙니다.  
  
### <a name="remarks"></a>주의  
 **소켓** 핸들 개체에 저장 됩니다 [m_hSocket](#m_hsocket) 데이터 멤버입니다.  
  
##  <a name="bind"></a>CAsyncSocket::Bind  
 소켓 로컬 주소를 연결 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSocketPort`  
 소켓 응용 프로그램을 식별 하는 포트입니다.  
  
 `lpszSocketAddress`  
 네트워크 주소 "128.56.22.8"와 같은 점으로 구분 된 번호입니다. 전달 된 **NULL** 이 매개 변수를 나타내는 문자열는 **CAsyncSocket** 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 이 소켓에 할당할 주소를 포함 하는 구조입니다.  
  
 `nSockAddrLen`  
 주소 길이 `lpSockAddr` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEADDRINUSE** 지정된 된 주소 이미를 사용 합니다. (참조는 **SO_REUSEADDR** 소켓 옵션 아래에서 [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** 는 `nSockAddrLen` 인수가 너무 작습니다 (의 크기 보다 작은 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조).  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 호출이 진행 중입니다.  
  
- **WSAEAFNOSUPPORT** 이 포트에서 지정된 된 주소 패밀리를 사용할 수 없습니다.  
  
- **WSAEINVAL** 소켓 주소에 이미 바인딩되어 있습니다.  
  
- `WSAENOBUFS`부족 합니다. 사용할 수 있는 버퍼를 너무 많은 연결이 있습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 이 루틴은 사용에 연결 되지 않은 데이터 그램 또는 스트림 소켓 전에 후속 **연결** 또는 `Listen` 호출 합니다. 서버 소켓의 수신 대기 포트 번호를 선택 하 고 쉽게 알려진 Windows 소켓을 호출 하 여 연결 요청을 허용 하려면, **바인딩할**합니다. **바인딩** 는 명명 되지 않은 소켓에 로컬 이름을 할당 하 여 소켓의 로컬 연결 (호스트 주소/포트 번호)을 설정 합니다.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 빈 소켓 개체를 만듭니다.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 개체를 생성 한 후 해당 **만들기** 만들려는 멤버 함수는 **소켓** 데이터 구조 및 해당 주소를 바인딩합니다. (Windows 소켓 통신을 수신 대기 소켓에서 사용 하는 소켓을 만들 때 서버 쪽에서의 **Accept** 호출을 호출 하지 않으면 **만들기** 해당 소켓에 대 한.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 소켓을 닫습니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 오류와 것에 대 한 참조는 실패 하는 더 이상 소켓 설명자를 해제 **WSAENOTSOCK**합니다. 기본 소켓에 대 한 마지막 참조 인 경우에 명명 관련된 정보 및 대기 중인된 데이터가 삭제 됩니다. 소켓 개체의 소멸자 호출 **닫기** 드립니다.  
  
 에 대 한 `CAsyncSocket`, 아니라 `CSocket`의 의미 체계 **닫기** 소켓 옵션에 영향을 받는 **SO_LINGER** 및 **SO_DONTLINGER**합니다. 자세한 내용은 멤버 함수를 참조 하십시오. `GetSockOpt`합니다.  
  
##  <a name="connect"></a>CAsyncSocket::Connect  
 연결 되지 않은 스트림 또는 데이터 그램 소켓에 대 한 연결을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszHostAddress`  
 이 개체가 연결 되는 소켓의 네트워크 주소: "형식인" 또는 "128.56.22.8" 등의 점으로 구분 된 숫자를 같은 컴퓨터 이름입니다.  
  
 `nHostPort`  
 소켓 응용 프로그램을 식별 하는 포트입니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 연결 된 소켓의 주소를 포함 하는 구조입니다.  
  
 `nSockAddrLen`  
 주소 길이 `lpSockAddr` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 오류 코드는이 경우 **WSAEWOULDBLOCK**, 및 응용 프로그램에 재정의 가능한 콜백을 사용 하는, 응용 프로그램 받습니다는 `OnConnect` 연결 작업이 완료 되었을 때 메시지. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEADDRINUSE** 지정된 된 주소 이미를 사용 합니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 호출이 진행 중입니다.  
  
- **WSAEADDRNOTAVAIL** 지정한 주소는 로컬 컴퓨터에서 사용할 수 없습니다.  
  
- **WSAEAFNOSUPPORT** 이 소켓으로 지정된 된 제품군에는 주소를 사용할 수 없습니다.  
  
- **WSAECONNREFUSED** 연결 시도가 거부 되었습니다.  
  
- **WSAEDESTADDRREQ** 대상 주소가 필요 합니다.  
  
- **WSAEFAULT** 는 `nSockAddrLen` 인수가 올바르지 않습니다.  
  
- **WSAEINVAL** 잘못 된 호스트 주소입니다.  
  
- **WSAEISCONN** 소켓이 이미 연결 되어 있습니다.  
  
- **WSAEMFILE** 더 이상 파일 설명자가 사용할 수 있습니다.  
  
- **WSAENETUNREACH** 지금은이 호스트에서 네트워크에 연결할 수 없습니다.  
  
- `WSAENOBUFS`사용할 수 있는 버퍼 공간이 없습니다. 소켓을 연결할 수 없습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAETIMEDOUT** 연결 연결을 설정 하지 않고 시간 초과 하려고 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시 되어 비차단 같이 연결을 즉시 완료할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 소켓에 바인딩되어 있지 않습니다., 고유 값 시스템, 로컬 연결에 할당 하 고 소켓으로 표시 되어 바인딩됩니다. 되는 경우 이름 구조체의 주소 필드는 모두&0;으로 **연결**&0;을 반환 합니다. 확장 정보를 가져오려면 오류를 호출 하는 `GetLastError` 멤버 함수입니다.  
  
 스트림 소켓에 대 한 (형식 **SOCK_STREAM**), 외부 호스트에 대 한 활성 연결이 시작 됩니다. 소켓 호출이 성공적으로 완료 되 면 소켓이 송신/수신 데이터에 있습니다.  
  
 데이터 그램 소켓에 대 한 (형식 **SOCK_DGRAM**), 기본 대상 설정 되어 다음에 사용 될 **보낼** 및 **수신** 호출 합니다.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 호출 된 **만들기** Windows 소켓을 만들고 연결 하는 소켓 개체를 생성 한 후 멤버 함수입니다.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSocketPort`  
 Windows 소켓 포트를 선택 하려는 경우에 소켓 또는 0 함께 사용 되는 잘 알려진 포트입니다.  
  
 `nSocketType`  
 **SOCK_STREAM** 또는 **SOCK_DGRAM**합니다.  
  
 `lEvent`  
 응용 프로그램은 관심 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.  
  
- **작업할** 읽기를 위한 준비 상태에 대 한 알림을 수신 하려면.  
  
- **FD_WRITE** 쓰기를 위한 준비에 대 한 알림을 수신 하려면.  
  
- **FD_OOB** 밴드의 범위를 벗어난 데이터에 대 한 알림을 수신 하려면.  
  
- **FD_ACCEPT** 들어오는 연결에 대 한 알림을 수신 하려면.  
  
- **FD_CONNECT** 완료 된 연결에 대 한 알림을 수신 하려면.  
  
- **FD_CLOSE** 소켓 닫기를 처리에 대 한 알림을 수신 하려면.  
  
 *lpszSockAddress*  
 "128.56.22.8" 등의 점으로 구분 된 숫자를 연결된 된 소켓의 네트워크 주소를 포함 하는 문자열에 대 한 포인터입니다. 전달 된 **NULL** 이 매개 변수를 나타내는 문자열는 **CAsyncSocket** 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEAFNOSUPPORT** 지정된 된 주소 패밀리에 지원 되지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEMFILE** 더 이상 파일 설명자가 사용할 수 있습니다.  
  
- `WSAENOBUFS`사용할 수 있는 버퍼 공간이 없습니다. 소켓을 만들 수 없습니다.  
  
- **WSAEPROTONOSUPPORT** 지정된 된 포트 지원 되지 않습니다.  
  
- **WSAEPROTOTYPE** 이 소켓에 대해 잘못 된 형식이 지정된 된 포트입니다.  
  
- **WSAESOCKTNOSUPPORT** 이 주소 패밀리에 지정된 된 소켓 형식이 지원 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 **만들** 호출 [소켓](#socket) 호출 성공 하면 [바인딩](#bind) 소켓을 바인딩하지 지정된 된 주소에 있습니다. 다음과 같은 소켓 유형이 지원 됩니다.  
  
- **SOCK_STREAM** 신뢰할 수 있는, 전이중, 연결 기반 바이트 스트림의 시퀀스를 제공 합니다. 인터넷 주소 패밀리에 대해 전송 제어 프로토콜 (TCP)을 사용합니다.  
  
- **SOCK_DGRAM** 최대 길이가 고정된 (일반적으로 작은)의 연결 없는, 안정적이 지 않은 패킷을 인 데이터 그램을 지원 합니다. 인터넷 주소 패밀리에 대해 (UDP (User Datagram Protocol)를 사용합니다.  
  
    > [!NOTE]
    >  **Accept** 멤버 함수는 비어 있는 새에 대 한 참조를 사용 `CSocket` 개체를 매개 변수로 합니다. 호출 하기 전에이 개체를 생성 해야 **Accept**합니다. 사항으로이 소켓 개체가 범위를 연결이 닫힙니다 사라지면 합니다. 호출 하지 마십시오 **만들기** 이 새 소켓 개체에 대 한 합니다.  
  
> [!IMPORTANT]
> **만들** 는 **하지** 스레드로부터 안전 합니다.  를 호출 하는 것 다중 스레드 환경에서 동시에 서로 다른 스레드에 의해 호출 될 수 있는 경우에 뮤텍스 또는 다른 동기화 잠금을 사용 하 여 각 호출을 보호 해야 합니다.  
  
 스트림 및 데이터 그램 소켓에 대 한 자세한 내용은 문서를 참조 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md) 및 [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md) 및 [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)합니다.  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 분리 하려면이 함수를 호출의 **소켓** 에서 처리는 `m_hSocket` 에서 데이터 멤버는 `CAsyncSocket` 개체 및 설정 `m_hSocket` 를 **NULL**합니다.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CAsyncSocket` 개체입니다.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>매개 변수  
 `hSocket`  
 소켓에 대 한 핸들을 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CAsyncSocket` 개체 또는 **NULL** 없을 경우 없는 `CAsyncSocket` 개체에 연결 된 `hSocket`합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 경우는 **소켓** 경우 처리는 `CAsyncSocket` 멤버 함수는 반환 된 핸들에는 개체가 연결 되지 않은, **NULL**합니다.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 실패 한 마지막 작업에 대 한 오류 상태를 가져오려면이 함수를 호출 합니다.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>반환 값  
 반환 값이이 스레드가 수행한 마지막 Windows 소켓 API 루틴에 대 한 오류 코드를 나타냅니다.  
  
### <a name="remarks"></a>주의  
 특정 멤버 함수, 오류가 발생 했음을 나타냅니다 때 `GetLastError` 적절 한 오류 코드를 검색 하려면를 호출 해야 합니다. 해당 오류 코드의 목록에 대 한 개별 멤버 함수 설명을 참조 하십시오.  
  
 오류 코드에 대 한 자세한 내용은 참조 [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)합니다.  
  
##  <a name="getpeername"></a>CAsyncSocket::GetPeerName  
 이 소켓 연결 되어 있는 피어 소켓의 주소를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>매개 변수  
 `rPeerAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rPeerPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조체 피어 소켓의 이름입니다.  
  
 `lpSockAddrLen`  
 주소 길이에 대 한 포인터 `lpSockAddr` (바이트)에서입니다. 반환이 이루어지고에 `lpSockAddrLen` 의 실제 크기를 포함 하는 인수 `lpSockAddr` 바이트 단위로 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수 만큼 크지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 호출이 진행 중입니다.  
  
- **WSAENOTCONN** 는 소켓이 연결 되지 않았습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 IPv6 주소를 처리 하려면 [CAsyncSocket::GetPeerNameEx](#getpeernameex)합니다.  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 이 소켓을 연결된 (핸들 IPv6 주소)는 피어 소켓의 주소를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>매개 변수  
 `rPeerAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rPeerPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수 만큼 크지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 호출이 진행 중입니다.  
  
- **WSAENOTCONN** 는 소켓이 연결 되지 않았습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 동일 [CAsyncSocket::GetPeerName](#getpeername) 오래 된 파일로 프로토콜 주소를 제외 하 고 i p v&6;을 처리 합니다.  
  
##  <a name="getsockname"></a>CAsyncSocket::GetSockName  
 이 소켓에 대 한 로컬 이름을 가져오는 함수를 호출 합니다.  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSocketAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rSocketPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조체는 소켓의 주소입니다.  
  
 `lpSockAddrLen`  
 주소 길이에 대 한 포인터 `lpSockAddr` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수 만큼 크지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEINVAL** 소켓에는 주소에 바인딩하지 않으면 **바인딩할**합니다.  
  
### <a name="remarks"></a>주의  
 이 호출은 때 특히 유용는 **연결** 호출 없이 수행 하는 **바인딩할** 이 호출에서 기준이 있는 시스템에서 설정한 로컬 연결을 확인할 수 있습니다 유일한 수단을 제공 하는 먼저;.  
  
 IPv6 주소를 처리 하려면 [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 이 소켓 (핸들 IPv6 주소)에 대 한 로컬 이름을 가져오는 함수를 호출 합니다.  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSocketAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rSocketPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수 만큼 크지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEINVAL** 소켓에는 주소에 바인딩하지 않으면 **바인딩할**합니다.  
  
### <a name="remarks"></a>주의  
 이 호출은 같습니다 [CAsyncSocket::GetSockName](#getsockname) 오래 된 파일로 프로토콜 주소를 제외 하 고 i p v&6;을 처리 합니다.  
  
 이 호출은 때 특히 유용는 **연결** 호출 없이 수행 하는 **바인딩할** 이 호출에서 기준이 있는 시스템에서 설정한 로컬 연결을 확인할 수 있습니다 유일한 수단을 제공 하는 먼저;.  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 소켓 옵션을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOptionName`  
 값은 검색할 소켓 옵션입니다.  
  
 `lpOptionValue`  
 요청 된 옵션의 값을 반환할 버퍼에 대 한 포인터입니다. 선택된 된 옵션은 연관 된 값은 버퍼에 반환 `lpOptionValue`합니다. 가리키는 정수 `lpOptionLen` (바이트)이이 버퍼의 크기를 원래 포함 되어 있어야 하 고 반환이 반환 되는 값의 크기를 설정할 수는 있습니다. 에 대 한 **SO_LINGER**를이 됩니다의 크기는 `LINGER` 구조체의 크기에 대 한 다른 모든 옵션 됩니다;는 **BOOL** 또는 `int`옵션에 따라 합니다. 옵션 및 주의 섹션에 해당 크기 목록을 참조 하십시오.  
  
 `lpOptionLen`  
 크기에 대 한 포인터는 `lpOptionValue` 바이트에서 버퍼입니다.  
  
 `nLevel`  
 이때 옵션 정의 되어 있으면 수준 지원 되는 유일한 수준은 **SOL_SOCKET** 및 **IPPROTO_TCP**합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 옵션으로 설정 되지 않았으면 경우 `SetSockOpt`, 다음 `GetSockOpt` 옵션에 대 한 기본 값을 반환 합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpOptionLen` 인수가 잘못 되었습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOPROTOOPT** 알 수 없거나 지원 되지 않는 옵션입니다. 특히, **SO_BROADCAST** 형식의 소켓에서 지원 되지 않습니다 **SOCK_STREAM**, 동안 **SO_ACCEPTCONN**, **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, 및 **SO_OOBINLINE** 형식의 소켓에서 지원 되지 않는 **SOCK_DGRAM**합니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 `GetSockOpt`모든 상태에서 모든 형식의 소켓와 연결 된 소켓 옵션에 대 한 현재 값을 검색 하 고 해당 결과 `lpOptionValue`합니다. 옵션 패킷과 대역폭을 벗어난 데이터 전송 등의 라우팅 등 소켓 작업을 영향을 줍니다.  
  
 다음 옵션에 대해 지원 됩니다 `GetSockOpt`합니다. 형식으로 주소가 지정 된 데이터의 형식을 식별 `lpOptionValue`합니다. **TCP_NODELAY** 옵션 수준을 사용 하 여 **IPPROTO_TCP**; 수준을 사용 하 여 다른 모든 옵션 **SOL_SOCKET**합니다.  
  
|값|형식|의미|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|소켓이 수신 중입니다.|  
|**SO_BROADCAST**|**BOOL**|소켓의 브로드캐스트 메시지 전송에 대 한 구성 됩니다.|  
|**SO_DEBUG**|**BOOL**|디버깅이 활성화 됩니다.|  
|**SO_DONTLINGER**|**BOOL**|True 이면는 **SO_LINGER** 옵션을 사용할 수 있습니다.|  
|**SO_DONTROUTE**|**BOOL**|라우팅이 비활성화 됩니다.|  
|**SO_ERROR**|`int`|오류 상태를 검색 하 고 지웁니다.|  
|**SO_KEEPALIVE**|**BOOL**|연결 유지 보내고 있습니다.|  
|**SO_LINGER**|**LINGER 구조체**|현재 링거 옵션을 반환합니다.|  
|**SO_OOBINLINE**|**BOOL**|정상 데이터 스트림에서 수신 중인 대역폭을 벗어난 데이터입니다.|  
|**SO_RCVBUF**|`int`|버퍼 크기를 받습니다.|  
|**SO_REUSEADDR**|**BOOL**|소켓이 이미 사용 중인 주소에 바인딩할 수 있습니다.|  
|**SO_SNDBUF**|`int`|버퍼 크기를 보냅니다.|  
|**SO_TYPE**|`int`|소켓의 유형 (예를 들어 **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|  
  
 버클리 소프트웨어 배포 (BSD) 옵션에 대 한 지원 되지 않습니다 `GetSockOpt` 됩니다.  
  
|값|형식|의미|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|하위 워터 마크를 수신 합니다.|  
|**SO_RCVTIMEO**|`int`|수신 제한 시간이 초과 합니다.|  
|**SO_SNDLOWAT**|`int`|하위 워터 마크를 보냅니다.|  
|**SO_SNDTIMEO**|`int`|제한 시간을 보냅니다.|  
|**IP_OPTIONS**||IP 헤더의 옵션을 가져옵니다.|  
|**TCP_MAXSEG**|`int`|TCP 최대 세그먼트 크기를 가져옵니다.|  
  
 호출 `GetSockOpt` 는 지원 되지 않는 옵션을 사용 하면 오류 코드 **WSAENOPROTOOPT** 에서 반환 되 고 `GetLastError`합니다.  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 소켓의 모드를 제어 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCommand`  
 소켓에서 수행 하는 명령입니다.  
  
 `lpArgument`  
 에 대 한 매개 변수에 대 한 포인터를 `lCommand`합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEINVAL** `lCommand` 유효한 명령이 아닙니다 또는 `lpArgument` 대 한 허용 가능한 매개 변수가 없는 `lCommand`되었거나 명령을 제공 하는 소켓의 형식에 적용할 수 없습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 이 루틴은 모든 상태에서 모든 소켓에서 사용할 수 있습니다. 가져오기 또는 연결 된 소켓, 프로토콜 및 통신 하위 시스템의 독립적인 운영 매개 변수를 검색 합니다. 사용 됩니다. 다음과 같은 명령이 지원 됩니다.  
  
- **FIONBIO** 소켓에 비차단 모드를 사용 하지 않도록 설정 하거나 사용 합니다. `lpArgument` 매개 변수를 가리키는 `DWORD`, 비차단 모드를 사용 하면&0;이 아니고 변수인 및 사용할 수 없게 하는 경우에는&0;입니다. 경우 `AsyncSelect` 사용 하려고 하면 다음 소켓에서 실행 된 **IOCtl** 소켓 차단 모드로 다시 설정에 실패 **WSAEINVAL**합니다. 소켓 차단 모드로 다시 설정 하 고 방지 하는 **WSAEINVAL** 오류, 응용 프로그램 먼저 해제 해야 `AsyncSelect` 를 호출 하 여 `AsyncSelect` 와 `lEvent` 매개 변수를 0으로, 다음 호출 **IOCtl**합니다.  
  
- **FIONREAD** 하나를 읽을 수 있는 바이트의 최대 수를 확인할 **수신** 이 소켓에서를 호출 합니다. `lpArgument` 매개 변수를 가리키는 `DWORD` 는 **IOCtl** 결과 저장 합니다. 이 소켓 형식인 경우 **SOCK_STREAM**를 **FIONREAD** 단일에서 읽을 수 있는 데이터의 총 크기를 반환 합니다. **수신**;이 일반적으로 동일한 소켓에서 대기열에 있는 총 데이터 양입니다. 이 소켓 형식인 경우 **SOCK_DGRAM**를 **FIONREAD** 소켓에서 대기열에 있는 첫 번째 데이터 그램의 크기를 반환 합니다.  
  
- **SIOCATMARK** 모든 대역폭을 벗어난 데이터 읽은 있는지 여부를 결정 합니다. 이 형식의 소켓에만 적용 됩니다 **SOCK_STREAM** 있는 모든 대역폭을 벗어난 데이터의 인라인 수신에 구성 된 ( **SO_OOBINLINE**). 없는 대역폭을 벗어난 데이터를 읽을 대기 중인 경우 작업이&0;이 아닌 값을 반환 합니다. 그렇지 않으면 0이 고, 다음 반환 **수신** 또는 `ReceiveFrom` 에서 수행 소켓 기호 앞의 "" 데이터 중 일부 또는 모두 검색 합니다; 응용 프로그램에서 사용 해야는 **SIOCATMARK** 데이터가 남아 있는지 여부를 결정 하는 작업입니다. 일반 데이터 앞에 "긴급" (대역) 데이터를 순서 대로 수신 됩니다. (유의 **수신** 또는 `ReceiveFrom` 대역의 및 일반 데이터는 동일한 호출에서을 혼합 해서는 안 됩니다.) `lpArgument` 매개 변수를 가리키는 `DWORD` 는 **IOCtl** 결과 저장 합니다.  
  
 이 함수는 하위 집합만 **ioctl()** 버클리 소켓에 사용 되 고 있습니다. 특히는 하는 것과 같은 명령은 **FIOASYNC**, 동안 **SIOCATMARK** 지원 되는 소켓 수준 명령입니다.  
  
##  <a name="listen"></a>CAsyncSocket::Listen  
 들어오는 연결 요청을 수신 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>매개 변수  
 *nConnectionBacklog*  
 보류 중인 연결 큐 증가할 수 있는 최대 길이입니다. 유효한 범위는 1에서 5 사이입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEADDRINUSE** 사용 중인 주소에서 수신 대기 하려고 합니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEINVAL** 소켓으로 바인딩되지 않은 **바인딩할** 또는 이미 연결 되어 있습니다.  
  
- **WSAEISCONN** 소켓이 이미 연결 되어 있습니다.  
  
- **WSAEMFILE** 더 이상 파일 설명자가 사용할 수 있습니다.  
  
- `WSAENOBUFS`사용할 수 있는 버퍼 공간이 없습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP** 참조 된 소켓을 지 원하는 유형이 아닙니다는 `Listen` 작업 합니다.  
  
### <a name="remarks"></a>주의  
 연결을 허용 하도록 소켓 먼저 만들어집니다 **만들기**, 들어오는 연결에 대 한 백로그 지정 된 `Listen`, 연결 허용 되며 다음 및 **Accept**합니다. `Listen`에 적용 됩니다 소켓 연결을 지 원하는, 즉, 형식과 **SOCK_STREAM**합니다. 이 소켓 들어오는 연결 된 승인 하 고 프로세스에 의해 승인 보류 중인 큐에 대기 하는 "수동" 모드에 배치 됩니다.  
  
 이 함수는 일반적으로 서버 (또는 연결을 허용 하려는 모든 응용 프로그램)가 사용 되어 한 번에 둘 이상의 연결 요청을 사용할 수 있는: 전체 큐와 연결 요청이 도착 하는 경우 클라이언트 오류가 발생 하는 **WSAECONNREFUSED**합니다.  
  
 `Listen`계속 해 서 사용할 수 있는 포트 (설명자) 없는 경우 논리적으로 작동을 시도 합니다. 그 큐를 비울 때까지 연결을 허용 합니다. 포트를 사용할 수 있는 경우 한 이후의 호출 `Listen` 또는 **Accept** 가능 하면 현재 또는 가장 최근 "백로그에" 큐를 다시 채우는 하 고 들어오는 연결을 수신 대기를 다시 시작 됩니다.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 포함 된 **소켓** 이 캡슐화 하는 소켓에 대 한 핸들 `CAsyncSocket` 개체입니다.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 호출 하 여 보류 중인 연결 요청 받을 수 있는 수신 대기 소켓에 알리기 위해 프레임 워크에서 호출 된 [Accept](#accept) 멤버 함수입니다.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnAccept` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 해당 프로세스에 의해 연결 된 소켓 닫혀 있는지이 소켓에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnClose` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAECONNRESET** 연결이 원격측에서 재설정 되었습니다.  
  
- **WSAECONNABORTED** 연결이 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 해당 연결 시도가 완료 되 면 성공적으로 또는 오류에서 소켓에이 연결에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnConnect` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAEADDRINUSE** 지정된 된 주소 이미를 사용 합니다.  
  
- **WSAEADDRNOTAVAIL** 지정한 주소는 로컬 컴퓨터에서 사용할 수 없습니다.  
  
- **WSAEAFNOSUPPORT** 이 소켓으로 지정된 된 제품군에는 주소를 사용할 수 없습니다.  
  
- **WSAECONNREFUSED** 연결 시도가 강제로 거부 되었습니다.  
  
- **WSAEDESTADDRREQ** 대상 주소가 필요 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수가 올바르지 않습니다.  
  
- **WSAEINVAL** 소켓 주소에 이미 바인딩되어 있습니다.  
  
- **WSAEISCONN** 소켓이 이미 연결 되어 있습니다.  
  
- **WSAEMFILE** 더 이상 파일 설명자가 사용할 수 있습니다.  
  
- **WSAENETUNREACH** 지금은이 호스트에서 네트워크에 연결할 수 없습니다.  
  
- `WSAENOBUFS`사용할 수 있는 버퍼 공간이 없습니다. 소켓을 연결할 수 없습니다.  
  
- **WSAENOTCONN** 는 소켓이 연결 되지 않았습니다.  
  
- **WSAENOTSOCK** 설명자는 파일, 소켓에 없습니다.  
  
- **WSAETIMEDOUT** 연결을 설정 하지 않고 연결 시도 시간이 초과 되었습니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` 알림 함수는 호출 되지 않습니다. 연결을 위해를 호출 하면 **연결**, (성공적으로 또는 오류에서)는 연결이 완료 된 경우 반환 합니다. MFC 구현 정보는 연결 알림을 처리 하는 방법입니다.  
  
 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAsyncSocket #&1;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 보내는 소켓에 대역폭을 벗어난 데이터를 보내는 수신 소켓에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnOutOfBandData` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
### <a name="remarks"></a>주의  
 대역폭을 벗어난 데이터는 연결 된 각 쌍 형식의 연결 된 소켓의 논리적으로 독립 채널 **SOCK_STREAM**합니다. 채널은 긴급 한 데이터를 보내도록 일반적으로 사용 됩니다.  
  
 MFC 클래스의 사용자가 있지만 대역폭을 벗어난 데이터 지원 `CAsyncSocket` 사용 해서는 안 됩니다. 더 쉬운 방법은 이러한 데이터를 전달 하기 위한 두 번째 소켓을 만드는 것입니다. 대역폭을 벗어난 데이터에 대 한 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 호출 하 여 검색할 수 있는 버퍼의 데이터는이 소켓에 알리기 위해 프레임 워크에서 호출 된 **수신** 멤버 함수입니다.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnReceive` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAsyncSocket #&2;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 호출 하 여 데이터 보내기 이제 수 소켓에 알리기 위해 프레임 워크에서 호출 된 **보낼** 멤버 함수입니다.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrorCode`  
 소켓에 대 한 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnSend` 멤버 함수:  
  
- **0** 성공적으로 실행 하는 함수입니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../../mfc/windows-sockets-socket-notifications.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAsyncSocket #&3;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 에 새 값을 할당 한 `CAsyncSocket` 개체입니다.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSrc`  
 기존에 대 한 참조 `CAsyncSocket` 개체입니다.  
  
### <a name="remarks"></a>주의  
 기존 복사 하려면이 함수를 호출 `CAsyncSocket` 개체를 다른 `CAsyncSocket` 개체입니다.  
  
##  <a name="operator_socket"></a>CAsyncSocket::operator 소켓  
 이 연산자를 사용 하 여 검색 하는 **소켓** 의 처리는 `CAsyncSocket` 개체입니다.  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우의 핸들은 **소켓** 그렇지 그렇지 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 Windows Api를 직접 호출 하 여 핸들을 사용할 수 있습니다.  
  
##  <a name="receive"></a>CAsyncSocket::Receive  
 소켓에서 데이터를 수신 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 들어오는 데이터에 대 한 버퍼입니다.  
  
 `nBufLen`  
 길이가 `lpBuf` (바이트)에서입니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_PEEK** 들어오는 데이터 보기입니다. 데이터 버퍼에 복사 되지만 입력된 큐에서 제거 되지 않습니다.  
  
- **MSG_OOB** 대역의 데이터를 처리 합니다.  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, **수신** 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAENOTCONN** 는 소켓이 연결 되지 않았습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 **수신** 후 소켓 `ShutDown` 와 호출 된 `nHow` 0 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 **수신** 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 데이터 그램에 지정된 된 버퍼에 맞게 너무 커서 및 잘렸습니다.  
  
- **WSAEINVAL** 소켓으로 바인딩되지 않은 **바인딩할**합니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 연결 된 스트림 또는 데이터 그램 소켓에 대 한 사용 하며 들어오는 데이터를 읽는 데 사용 됩니다.  
  
 형식의 소켓에 대 한 **SOCK_STREAM**에서 제공 하는 버퍼의 크기 최대 현재 사용할 수 있는 많은 정보 반환 됩니다. 소켓 대역폭을 벗어난 데이터의 인라인 수신에 구성 된 경우 (소켓 옵션 **SO_OOBINLINE**) 및 대역폭을 벗어난 데이터를 읽고, 밴드를만 데이터가 반환 됩니다. 응용 프로그램에서 사용할 수는 **IOCtlSIOCATMARK** 옵션 또는 [OnOutOfBandData](#onoutofbanddata) 읽을 밴드를 더 데이터가 남아 있는지 여부를 확인 하려면.  
  
 데이터 그램 소켓에 대 한 데이터는 지정 된 버퍼의 크기까지 첫 번째 큐에 배치 된 데이터 그램에서 추출 됩니다. 데이터 그램을 지정 된 버퍼 보다 큰 경우 데이터 그램의 첫 번째 부분으로 된 버퍼가 채워집니다, 초과 데이터는 손실 및 **수신** 의 값을 반환 **SOCKET_ERROR** 로 설정 하는 오류 코드로 인해 **WSAEMSGSIZE**합니다. 값이 소켓에 없는 들어오는 데이터를 사용할 수 **SOCKET_ERROR** 로 설정 하는 오류 코드가 반환 됩니다 **WSAEWOULDBLOCK**합니다. [OnReceive](#onreceive) 더 많은 데이터가 도착할 시기를 결정 하는 콜백 함수를 사용할 수 있습니다.  
  
 소켓 형식인 경우 **SOCK_STREAM** 원격 대화 상대에 대 한 연결 정상적으로 종료, 및는 **수신** 받은 0 바이트와 함께 즉시 완료 됩니다. 연결 다시 설정 하는 경우는 **수신** 오류와 함께 실패 합니다 **WSAECONNRESET**합니다.  
  
 **수신** 각 시간에 대해 한 번만 호출 해야 [CAsyncSocket::OnReceive](#onreceive) 호출 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CAsyncSocket::OnReceive](#onreceive)합니다.  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 데이터 그램을 수신 하 고에서 원본 주소를 저장 하려면이 멤버 함수를 호출 하는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조 또는 `rSocketAddress`합니다.  
  
```  
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);

 
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 들어오는 데이터에 대 한 버퍼입니다.  
  
 `nBufLen`  
 길이가 `lpBuf` (바이트)에서입니다.  
  
 `rSocketAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rSocketPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 반환 시 원본 주소를 보유 하는 구조입니다.  
  
 `lpSockAddrLen`  
 원본 주소에서의 길이에 대 한 포인터 `lpSockAddr` (바이트)에서입니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_PEEK** 들어오는 데이터 보기입니다. 데이터 버퍼에 복사 되지만 입력된 큐에서 제거 되지 않습니다.  
  
- **MSG_OOB** 대역의 데이터를 처리 합니다.  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, `ReceiveFrom` 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 `GetLastError`합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수가 잘못 되었습니다:는 `lpSockAddr` 버퍼가 너무 작아서 피어 주소입니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEINVAL** 소켓으로 바인딩되지 않은 **바인딩할**합니다.  
  
- **WSAENOTCONN** 소켓이 연결 되지 않은 ( **SOCK_STREAM** 만).  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 `ReceiveFrom` 후 소켓 `ShutDown` 와 호출 된 `nHow` 0 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 `ReceiveFrom` 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 데이터 그램에 지정된 된 버퍼에 맞게 너무 커서 및 잘렸습니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 (연결된 수 있음)는 소켓에서 들어오는 데이터를 읽고 데이터를 보낸 주소에 사용 됩니다.  
  
 IPv6 주소를 처리 하려면 [CAsyncSocket::ReceiveFromEx](#receivefromex)합니다.  
  
 형식의 소켓에 대 한 **SOCK_STREAM**에서 제공 하는 버퍼의 크기 최대 현재 사용할 수 있는 많은 정보 반환 됩니다. 소켓 대역폭을 벗어난 데이터의 인라인 수신에 구성 된 경우 (소켓 옵션 **SO_OOBINLINE**) 및 대역폭을 벗어난 데이터를 읽고, 밴드를만 데이터가 반환 됩니다. 응용 프로그램에서 사용할 수는 **IOCtlSIOCATMARK** 옵션 또는 `OnOutOfBandData` 읽을 밴드를 더 데이터가 남아 있는지 여부를 확인 하려면. `lpSockAddr` 및 `lpSockAddrLen` 에 대 한 매개 변수는 무시 **SOCK_STREAM** 소켓.  
  
 데이터 그램 소켓에 대 한 데이터는 지정 된 버퍼의 크기까지 첫 번째 큐에 배치 된 데이터 그램에서 추출 됩니다. 데이터 그램을 지정 된 버퍼 보다 큰 경우 메시지의 첫 번째 부분으로 된 버퍼가 채워집니다, 초과 데이터는 손실 및 `ReceiveFrom` 의 값을 반환 **SOCKET_ERROR** 로 설정 하는 오류 코드로 인해 **WSAEMSGSIZE**합니다.  
  
 경우 `lpSockAddr` 이 값은&0;와 소켓 종류가 **SOCK_DGRAM**, 데이터를 전송 하는 소켓의 네트워크 주소에 해당 요소에 복사 됩니다 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조입니다. 가리키는 값 `lpSockAddrLen` 이 구조체의 크기로 초기화 되 고 거기에 저장 하는 주소의 실제 크기를 나타내기 위해 반환이 수정 됩니다. 들어오는 데이터가 없는 소켓에서 사용할 수 있는 경우는 `ReceiveFrom` 소켓이 아닌 경우 도착 하는 데이터에 대 한 호출은 기다립니다 비차단 합니다. 이 경우 값은 **SOCKET_ERROR** 로 설정 하는 오류 코드가 반환 됩니다 **WSAEWOULDBLOCK**합니다. `OnReceive` 콜백 도착 시간을 확인할 더 많은 데이터를 사용할 수 있습니다.  
  
 소켓 형식인 경우 **SOCK_STREAM** 원격 대화 상대에 대 한 연결 정상적으로 종료, 및는 `ReceiveFrom` 받은 0 바이트와 함께 즉시 완료 됩니다.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 데이터 그램을 수신 하 고에서 원본 주소를 저장 하려면이 멤버 함수를 호출 하는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조 또는 `rSocketAddress` (IPv6 주소 처리).  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 들어오는 데이터에 대 한 버퍼입니다.  
  
 `nBufLen`  
 길이가 `lpBuf` (바이트)에서입니다.  
  
 `rSocketAddress`  
 에 대 한 참조는 `CString` 점선으로 된 숫자 IP 주소를 받는 개체입니다.  
  
 `rSocketPort`  
 에 대 한 참조는 **UINT** 포트를 저장 하는 합니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_PEEK** 들어오는 데이터 보기입니다. 데이터 버퍼에 복사 되지만 입력된 큐에서 제거 되지 않습니다.  
  
- **MSG_OOB** 대역의 데이터를 처리 합니다.  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, `ReceiveFromEx` 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 `GetLastError`합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** 는 `lpSockAddrLen` 인수가 잘못 되었습니다:는 `lpSockAddr` 버퍼가 너무 작아서 피어 주소입니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEINVAL** 소켓으로 바인딩되지 않은 **바인딩할**합니다.  
  
- **WSAENOTCONN** 소켓이 연결 되지 않은 ( **SOCK_STREAM** 만).  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 `ReceiveFromEx` 후 소켓 `ShutDown` 와 호출 된 `nHow` 0 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 `ReceiveFromEx` 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 데이터 그램에 지정된 된 버퍼에 맞게 너무 커서 및 잘렸습니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 (연결된 수 있음)는 소켓에서 들어오는 데이터를 읽고 데이터를 보낸 주소에 사용 됩니다.  
  
 이 함수는 동일 [CAsyncSocket::ReceiveFrom](#receivefrom) 오래 된 파일로 프로토콜 주소를 제외 하 고 i p v&6;을 처리 합니다.  
  
 형식의 소켓에 대 한 **SOCK_STREAM**에서 제공 하는 버퍼의 크기 최대 현재 사용할 수 있는 많은 정보 반환 됩니다. 소켓 대역폭을 벗어난 데이터의 인라인 수신에 구성 된 경우 (소켓 옵션 **SO_OOBINLINE**) 및 대역폭을 벗어난 데이터를 읽고, 밴드를만 데이터가 반환 됩니다. 응용 프로그램에서 사용할 수는 **IOCtlSIOCATMARK** 옵션 또는 `OnOutOfBandData` 읽을 밴드를 더 데이터가 남아 있는지 여부를 확인 하려면. `lpSockAddr` 및 `lpSockAddrLen` 에 대 한 매개 변수는 무시 **SOCK_STREAM** 소켓.  
  
 데이터 그램 소켓에 대 한 데이터는 지정 된 버퍼의 크기까지 첫 번째 큐에 배치 된 데이터 그램에서 추출 됩니다. 데이터 그램을 지정 된 버퍼 보다 큰 경우 메시지의 첫 번째 부분으로 된 버퍼가 채워집니다, 초과 데이터는 손실 및 `ReceiveFromEx` 의 값을 반환 **SOCKET_ERROR** 로 설정 하는 오류 코드로 인해 **WSAEMSGSIZE**합니다.  
  
 경우 `lpSockAddr` 이 값은&0;와 소켓 종류가 **SOCK_DGRAM**, 데이터를 전송 하는 소켓의 네트워크 주소에 해당 요소에 복사 됩니다 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조입니다. 가리키는 값 `lpSockAddrLen` 이 구조체의 크기로 초기화 되 고 거기에 저장 하는 주소의 실제 크기를 나타내기 위해 반환이 수정 됩니다. 들어오는 데이터가 없는 소켓에서 사용할 수 있는 경우는 `ReceiveFromEx` 소켓이 아닌 경우 도착 하는 데이터에 대 한 호출은 기다립니다 비차단 합니다. 이 경우 값은 **SOCKET_ERROR** 로 설정 하는 오류 코드가 반환 됩니다 **WSAEWOULDBLOCK**합니다. `OnReceive` 콜백 도착 시간을 확인할 더 많은 데이터를 사용할 수 있습니다.  
  
 소켓 형식인 경우 **SOCK_STREAM** 원격 대화 상대에 대 한 연결 정상적으로 종료, 및는 `ReceiveFromEx` 받은 0 바이트와 함께 즉시 완료 됩니다.  
  
##  <a name="send"></a>CAsyncSocket::Send  
 연결 된 소켓에서 데이터를 전송 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 전송할 데이터를 포함 하는 버퍼입니다.  
  
 `nBufLen`  
 에 있는 데이터의 길이 `lpBuf` (바이트)에서입니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_DONTROUTE** 데이터 라우팅 적용 안 되도록 지정 합니다. Windows 소켓 공급 업체가이 플래그를 무시 하도록 선택할 수 있습니다.  
  
- **MSG_OOB** 대역폭을 벗어난 데이터 보내기 ( **SOCK_STREAM** 만).  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, **보낼** 전송 되는 문자의 총 수를 반환 합니다. (표시 된 수보다 작을 수 있습니다이 `nBufLen`.) 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEACCES** 요청된 된 주소는 브로드캐스트 주소 하지만 적절 한 플래그를 설정 하지 않았습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEFAULT** 는 `lpBuf` 인수는 사용자 주소 공간의 유효한 부분에 없습니다.  
  
- **WSAENETRESET** Windows 소켓 구현을 삭제 하기 때문에 대 한 연결을 다시 설정 해야 합니다.  
  
- `WSAENOBUFS`Windows 소켓 구현이 버퍼 교착 상태를 보고합니다.  
  
- **WSAENOTCONN** 는 소켓이 연결 되지 않았습니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 **보낼** 후 소켓 `ShutDown` 와 호출 된 `nHow` 1 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 요청 된 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 소켓 유형입니다 **SOCK_DGRAM**, 및 데이터 그램 Windows 소켓 구현에 의해 지원 되는 최대값 보다 큽니다.  
  
- **WSAEINVAL** 소켓으로 바인딩되지 않은 **바인딩할**합니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
### <a name="remarks"></a>주의  
 **보내기** 에서 연결 된 스트림 또는 데이터 그램 소켓에 보내는 데이터를 작성 하는 데 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷의 최대 IP 패킷 크기를 초과 하는 **iMaxUdpDg** 요소에는 [WSADATA](../../mfc/reference/wsadata-structure.md) 에서 반환 된 구조 `AfxSocketInit`합니다. 데이터가 너무 길어 기본 프로토콜 오류를 원자적으로 통과할 경우 **WSAEMSGSIZE** 를 통해 반환 `GetLastError`, 데이터가 전송 됩니다.  
  
 경우 데이터 그램 소켓 성공적으로 완료 한 **보내기** 데이터가 성공적으로 배달 하는 것을 표시 하지 않습니다.  
  
 `CAsyncSocket` 형식의 개체 **SOCK_STREAM**, 쓴 바이트 수, 로컬 및 외부 호스트에 대 한 버퍼 가용성에 따라 요청 된 길이 1 사이의 수 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CAsyncSocket::OnSend](#onsend)합니다.  
  
##  <a name="sendto"></a>CAsyncSocket::SendTo  
 특정 대상에 데이터를 전송 하려면이 멤버 함수를 호출 합니다.  
  
```  
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);

 
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 전송할 데이터를 포함 하는 버퍼입니다.  
  
 `nBufLen`  
 에 있는 데이터의 길이 `lpBuf` (바이트)에서입니다.  
  
 `nHostPort`  
 소켓 응용 프로그램을 식별 하는 포트입니다.  
  
 `lpszHostAddress`  
 이 개체가 연결 되는 소켓의 네트워크 주소: "형식인" 또는 "128.56.22.8" 등의 점으로 구분 된 숫자를 같은 컴퓨터 이름입니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_DONTROUTE** 데이터 라우팅 적용 안 되도록 지정 합니다. Windows 소켓 공급 업체가이 플래그를 무시 하도록 선택할 수 있습니다.  
  
- **MSG_OOB** 대역폭을 벗어난 데이터 보내기 ( **SOCK_STREAM** 만).  
  
 `lpSockAddr`  
 에 대 한 포인터는 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 대상 소켓의 주소를 포함 하는 구조입니다.  
  
 `nSockAddrLen`  
 주소 길이 `lpSockAddr` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, `SendTo` 전송 되는 문자의 총 수를 반환 합니다. (표시 된 수보다 작을 수 있습니다이 `nBufLen`.) 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEACCES** 요청된 된 주소는 브로드캐스트 주소 하지만 적절 한 플래그를 설정 하지 않았습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEFAULT** 는 `lpBuf` 또는 `lpSockAddr` 매개 변수 사용자 주소 공간에 속하지 않는 또는 `lpSockAddr` 인수가 너무 작습니다 (의 크기 보다 작은 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조).  
  
- **WSAEINVAL** 호스트 이름이 잘못 되었습니다.  
  
- **WSAENETRESET** Windows 소켓 구현을 삭제 하기 때문에 대 한 연결을 다시 설정 해야 합니다.  
  
- `WSAENOBUFS`Windows 소켓 구현이 버퍼 교착 상태를 보고합니다.  
  
- **WSAENOTCONN** 소켓이 연결 되지 않은 ( **SOCK_STREAM** 만).  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 `SendTo` 후 소켓 `ShutDown` 와 호출 된 `nHow` 1 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 요청 된 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 소켓 유형입니다 **SOCK_DGRAM**, 및 데이터 그램 Windows 소켓 구현에 의해 지원 되는 최대값 보다 큽니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
- **WSAEADDRNOTAVAIL** 지정한 주소는 로컬 컴퓨터에서 사용할 수 없습니다.  
  
- **WSAEAFNOSUPPORT** 이 소켓으로 지정된 된 제품군에는 주소를 사용할 수 없습니다.  
  
- **WSAEDESTADDRREQ** 대상 주소가 필요 합니다.  
  
- **WSAENETUNREACH** 지금은이 호스트에서 네트워크에 연결할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 `SendTo`스트림 또는 데이터 그램 소켓에서 사용 되 고 소켓에 보내는 데이터를 작성 하는 데 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷의 최대 IP 패킷 크기를 초과 하는 **iMaxUdpDg** 요소에는 [WSADATA](../../mfc/reference/wsadata-structure.md) 구조 작성 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)합니다. 데이터가 너무 길어 기본 프로토콜 오류를 원자적으로 통과할 경우 **WSAEMSGSIZE** 반환 되 면 데이터가 전송 됩니다.  
  
 성공적으로 완료는 `SendTo` 데이터가 성공적으로 배달 하는 것을 표시 하지 않습니다.  
  
 `SendTo`에 사용 되는 **SOCK_DGRAM** 데이터 그램으로 식별 되는 특정 소켓 보내려고 소켓은 `lpSockAddr` 매개 변수입니다.  
  
 브로드캐스트를 보내도록 (에 **SOCK_DGRAM** 만), 주소는 `lpSockAddr` 특수 IP 주소를 사용 하 여 매개 변수를 생성 해야 **INADDR_BROADCAST** (WINSOCK의 Windows 소켓 헤더 파일에 정의 합니다. H)와 함께 원하는 포트 번호입니다. 또는 경우에는 `lpszHostAddress` 매개 변수는 **NULL**, 소켓 브로드캐스트에 대 한 구성 됩니다. 조각화가 발생할 수 크기를 초과 하는 브로드캐스트 데이터 그램에 일반적으로 바람직하지 않습니다 (헤더 제외)는 데이터 그램의 데이터 부분 512 바이트를 넘지 않아야을 의미 합니다.  
  
 IPv6 주소를 처리 하려면 [CAsyncSocket::SendToEx](#sendtoex)합니다.  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 이 데이터를 특정 대상 (핸들 IPv6 주소)를 보내는 함수를 호출 합니다.  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 전송할 데이터를 포함 하는 버퍼입니다.  
  
 `nBufLen`  
 에 있는 데이터의 길이 `lpBuf` (바이트)에서입니다.  
  
 `nHostPort`  
 소켓 응용 프로그램을 식별 하는 포트입니다.  
  
 `lpszHostAddress`  
 이 개체가 연결 되는 소켓의 네트워크 주소: "형식인" 또는 "128.56.22.8" 등의 점으로 구분 된 숫자를 같은 컴퓨터 이름입니다.  
  
 `nFlags`  
 호출 하는 방법을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 `nFlags` 매개 변수입니다. 후자는 c + +는 다음 값 중 하나를 결합 하 여 생성 됩니다 `OR` 연산자:  
  
- **MSG_DONTROUTE** 데이터 라우팅 적용 안 되도록 지정 합니다. Windows 소켓 공급 업체가이 플래그를 무시 하도록 선택할 수 있습니다.  
  
- **MSG_OOB** 대역폭을 벗어난 데이터 보내기 ( **SOCK_STREAM** 만).  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하지 않으면, `SendToEx` 전송 되는 문자의 총 수를 반환 합니다. (표시 된 수보다 작을 수 있습니다이 `nBufLen`.) 그렇지 않으면 값이 **SOCKET_ERROR** 반환 되 면 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEACCES** 요청된 된 주소는 브로드캐스트 주소 하지만 적절 한 플래그를 설정 하지 않았습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEFAULT** 는 `lpBuf` 또는 `lpSockAddr` 매개 변수 사용자 주소 공간에 속하지 않는 또는 `lpSockAddr` 인수가 너무 작습니다 (의 크기 보다 작은 [SOCKADDR](../../mfc/reference/sockaddr-structure.md) 구조).  
  
- **WSAEINVAL** 호스트 이름이 잘못 되었습니다.  
  
- **WSAENETRESET** Windows 소켓 구현을 삭제 하기 때문에 대 한 연결을 다시 설정 해야 합니다.  
  
- `WSAENOBUFS`Windows 소켓 구현이 버퍼 교착 상태를 보고합니다.  
  
- **WSAENOTCONN** 소켓이 연결 되지 않은 ( **SOCK_STREAM** 만).  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
- **WSAEOPNOTSUPP MSG_OOB** 을 지정 하지 않으면이 소켓 형식의 **SOCK_STREAM**합니다.  
  
- **WSAESHUTDOWN** 소켓이 종료 되었습니다; 호출할 수 없는 `SendToEx` 후 소켓 `ShutDown` 와 호출 된 `nHow` 1 또는 2로 설정 합니다.  
  
- **WSAEWOULDBLOCK** 소켓 표시가 같이 비차단 및 요청 된 작업이 중단 됩니다.  
  
- **WSAEMSGSIZE** 소켓 유형입니다 **SOCK_DGRAM**, 및 데이터 그램 Windows 소켓 구현에 의해 지원 되는 최대값 보다 큽니다.  
  
- **WSAECONNABORTED** 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.  
  
- **WSAECONNRESET** 가상 회로가 원격 쪽에서 재설정 되었습니다.  
  
- **WSAEADDRNOTAVAIL** 지정한 주소는 로컬 컴퓨터에서 사용할 수 없습니다.  
  
- **WSAEAFNOSUPPORT** 이 소켓으로 지정된 된 제품군에는 주소를 사용할 수 없습니다.  
  
- **WSAEDESTADDRREQ** 대상 주소가 필요 합니다.  
  
- **WSAENETUNREACH** 지금은이 호스트에서 네트워크에 연결할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 동일 [CAsyncSocket::SendTo](#sendto) 오래 된 파일로 프로토콜 주소를 제외 하 고 i p v&6;을 처리 합니다.  
  
 `SendToEx`스트림 또는 데이터 그램 소켓에서 사용 되 고 소켓에 보내는 데이터를 작성 하는 데 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷의 최대 IP 패킷 크기를 초과 하는 **iMaxUdpDg** 요소에는 [WSADATA](../../mfc/reference/wsadata-structure.md) 구조 작성 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)합니다. 데이터가 너무 길어 기본 프로토콜 오류를 원자적으로 통과할 경우 **WSAEMSGSIZE** 반환 되 면 데이터가 전송 됩니다.  
  
 성공적으로 완료는 `SendToEx` 데이터가 성공적으로 배달 하는 것을 표시 하지 않습니다.  
  
 `SendToEx`에 사용 되는 **SOCK_DGRAM** 데이터 그램으로 식별 되는 특정 소켓 보내려고 소켓은 `lpSockAddr` 매개 변수입니다.  
  
 브로드캐스트를 보내도록 (에 **SOCK_DGRAM** 만), 주소는 `lpSockAddr` 특수 IP 주소를 사용 하 여 매개 변수를 생성 해야 **INADDR_BROADCAST** (WINSOCK의 Windows 소켓 헤더 파일에 정의 합니다. H)와 함께 원하는 포트 번호입니다. 또는 경우에는 `lpszHostAddress` 매개 변수는 **NULL**, 소켓 브로드캐스트에 대 한 구성 됩니다. 조각화가 발생할 수 크기를 초과 하는 브로드캐스트 데이터 그램에 일반적으로 바람직하지 않습니다 (헤더 제외)는 데이터 그램의 데이터 부분 512 바이트를 넘지 않아야을 의미 합니다.  
  
##  <a name="setsockopt"></a>CAsyncSocket::SetSockOpt  
 이 소켓 옵션을 설정 하려면 함수를 호출 합니다.  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOptionName`  
 값이 설정 되어야 하는 소켓 옵션입니다.  
  
 `lpOptionValue`  
 요청된 된 옵션에 대 한 값은 지정 된 버퍼에 대 한 포인터입니다.  
  
 `nOptionLen`  
 크기는 `lpOptionValue` 바이트에서 버퍼입니다.  
  
 `nLevel`  
 이때 옵션 정의 되어 있으면 수준 지원 되는 유일한 수준은 **SOL_SOCKET** 및 **IPPROTO_TCP**합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEFAULT** `lpOptionValue` 프로세스 주소 공간의 유효한 부분에 아닙니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAEINVAL** `nLevel` 유효 하지 않거나 또는에 있는 정보 `lpOptionValue` 올바르지 않습니다.  
  
- **WSAENETRESET** 연결 시간이 초과 될 때 **SO_KEEPALIVE** 설정 됩니다.  
  
- **WSAENOPROTOOPT** 알 수 없거나 지원 되지 않는 옵션입니다. 특히, **SO_BROADCAST** 형식의 소켓에서 지원 되지 않습니다 **SOCK_STREAM**, 동안 **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, 및 **SO_OOBINLINE** 형식의 소켓에서 지원 되지 않는 **SOCK_DGRAM**합니다.  
  
- **WSAENOTCONN** 연결이 재설정 될 때 **SO_KEEPALIVE** 설정 됩니다.  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 `SetSockOpt`모든 상태에서 모든 형식의 소켓와 연결 된 소켓 옵션에 대 한 현재 값을 설정 합니다. 옵션 여러 프로토콜 수준에서 존재할 수 있지만이 사양은 "소켓" 최상위 수준에 존재 하는 옵션을 정의 합니다. 옵션 브로드캐스트 메시지는 소켓에서 전송할 수 있으며 등 여부 긴급된 데이터 정상 데이터 스트림에 수신 되는 여부와 같은 소켓 작업을 영향을 줍니다.  
  
 소켓 옵션의 두 종류가 있습니다: 기능 또는 동작을 설정 하거나 해제 하는 부울 옵션 및는 정수 값 또는 구조 해야 하는 옵션이 있습니다. 부울 옵션을 사용 하도록 설정 하려면 `lpOptionValue`&0;이 아닌 정수를 가리킵니다. 옵션을 사용 하지 않도록 설정 하려면 `lpOptionValue`&0;과 같은 정수를 가리킵니다. `nOptionLen`같아야 **sizeof (bool)** 부울 옵션입니다. 다른 옵션을 `lpOptionValue` 정수 또는 옵션의 경우 원하는 값이 포함 된 구조체를 가리키는 및 `nOptionLen` 정수 또는 구조체의 길이입니다.  
  
 **SO_LINGER** 때 수행 되는 동작 보내지 데이터는 큐에 대기 소켓에서 컨트롤 및 **닫습니다** 함수가 호출 되어 소켓을 닫습니다.  
  
 기본적으로는 소켓을 바인딩할 수 없습니다 (참조 [바인딩할](#bind)) 이미 사용 중인 로컬 주소에 있습니다. 그러나 경우에 따라 경우도 있습니다 "다시 사용"이 방법으로 주소입니다. 모든 연결이 로컬 및 원격 주소의 조합으로 고유 하 게 식별 됩니다 이므로 원격 주소는 다른으로 동일한 로컬 주소에 바인딩된 두 개의 소켓 있는 문제가 없습니다.  
  
 Windows 소켓 구현을 알리기 위해 하는 **바인딩** 원하는 주소가 이미 다른 소켓에서 사용 중 이므로 소켓에 대 한 호출을 허용 되지 해야 응용 프로그램 설정 해야 합니다는 **SO_REUSEADDR** 소켓 실행 하기 전에 소켓에 대 한 옵션의 **바인딩할** 호출 합니다. 옵션의 시간에만 해석 됩니다는 **바인딩할** 호출: 필요한 경우가 아니라면 따라서 무해) (그러나 하지는 기존 주소에 바인딩해야 하는 소켓 옵션을 설정 하려면 설정 하거나 다음 옵션을 다시 설정 하 고는 **바인딩할** 호출에이에 영향을 주지 또는 다른 소켓.  
  
 Windows 소켓 구현을 설정 하 여 "유지" 패킷 전송 제어 프로토콜 (TCP) 연결에 사용할 수 있게 응용 프로그램이 요청할 수는 **SO_KEEPALIVE** 소켓 옵션입니다. Windows 소켓 구현이 필요 keep-alive의 사용을 지원 하지: 정확한 의미는 구현과 관련 되지만 RFC 1122의 4.2.3.6를 준수 해야 그렇지 않으면: "인터넷 호스트에 대 한 요구 사항-통신 계층과." 연결이 끊어질 경우 "연결 유지"의 결과로 오류 코드 **WSAENETRESET** 소켓에서 진행 중인 모든 호출에 반환 되 고 모든 후속 호출은 실패 하며 **WSAENOTCONN**합니다.  
  
 **TCP_NODELAY** 옵션 Nagle 알고리즘을 비활성화 합니다. Nagle 알고리즘은 큰 패킷을 보낼 수까지 승인 되지 않은 송신 데이터를 버퍼링 하 여 호스트를 통해 전송 하는 작은 패킷의 수를 줄이기 위해 사용 됩니다. 그러나 일부 응용 프로그램에 대 한이 알고리즘을 저해할 수 성능 및 **TCP_NODELAY** 해제 데 사용할 수 있습니다. 응용 프로그램 기록기를 설정 하지 않아야 **TCP_NODELAY** 아닌 경우이 따른 영향을 잘 이해 하 고 원하는 설정을 이후 **TCP_NODELAY** 네트워크 성능에 크게 저하 될 수 있습니다. **TCP_NODELAY** 유일한 수준을 사용 하는 소켓 옵션을 지원 **IPPROTO_TCP**; 수준을 사용 하 여 다른 모든 옵션 **SOL_SOCKET**합니다.  
  
 Windows 소켓 공급의 일부 구현 디버그 정보를 출력 하는 경우는 **SO_DEBUG** 옵션은 응용 프로그램으로 설정 합니다.  
  
 다음 옵션에 대해 지원 됩니다 `SetSockOpt`합니다. 형식으로 주소가 지정 된 데이터의 형식을 식별 `lpOptionValue`합니다.  
  
|값|형식|의미|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|소켓의 브로드캐스트 메시지의 전송을 허용 합니다.|  
|**SO_DEBUG**|**BOOL**|디버깅 정보를 기록합니다.|  
|**SO_DONTLINGER**|**BOOL**|차단 하지 않도록 **닫기** 보내지 않은 데이터를 보낼 때까지 대기 합니다. 이 옵션을 설정 하는 것이 설정에 해당 하는 **SO_LINGER** 와 **l_onoff**&0;으로 설정 합니다.|  
|**SO_DONTROUTE**|**BOOL**|라우팅 하지 않습니다: 인터페이스에 직접 전송 합니다.|  
|**SO_KEEPALIVE**|**BOOL**|연결 유지를 보냅니다.|  
|**SO_LINGER**|**LINGER 구조체**|지연 **닫기** 데이터가 있는지 보내지 않은 경우.|  
|**SO_OOBINLINE**|**BOOL**|정상 데이터 스트림에서 대역폭을 벗어난 데이터를 수신 합니다.|  
|**SO_RCVBUF**|`int`|수신 버퍼 크기를 지정 합니다.|  
|**SO_REUSEADDR**|**BOOL**|소켓이 이미 사용 중인 주소에 바인딩될 수 있도록 합니다. (See [Bind](#bind).)|  
|**SO_SNDBUF**|`int`|전송에 대 한 버퍼 크기를 지정 합니다.|  
|**TCP_NODELAY**|**BOOL**|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|  
  
 버클리 소프트웨어 배포 (BSD) 옵션에 대 한 지원 되지 않습니다 `SetSockOpt` 됩니다.  
  
|값|형식|의미|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|소켓이 수신 중|  
|**SO_ERROR**|`int`|오류 상태를 가져온 다음의 선택을 취소 합니다.|  
|**SO_RCVLOWAT**|`int`|하위 워터 마크를 수신 합니다.|  
|**SO_RCVTIMEO**|`int`|수신 시간 제한|  
|**SO_SNDLOWAT**|`int`|하위 워터 마크를 보냅니다.|  
|**SO_SNDTIMEO**|`int`|제한 시간을 보냅니다.|  
|**SO_TYPE**|`int`|소켓의 형식입니다.|  
|**IP_OPTIONS**||IP 헤더에서 옵션 필드를 설정 합니다.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 호출을 사용 하지 않도록 설정 하려면이 멤버 함수를 보내고 받는 소켓에 또는 둘 다.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>매개 변수  
 `nHow`  
 어떤 유형의 작업에 설명 하는 플래그를 더 이상 허용 되도록 다음 열거형된 값을 사용 하 여:  
  
- **수신 = 0**  
  
- **보냅니다 = 1**  
  
- **모두 = 2**  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 특정 오류 코드를 검색할 수를 호출 하 여 [GetLastError](#getlasterror)합니다. 다음과 같은 오류가이 멤버 함수에 적용 됩니다.  
  
- **WSANOTINITIALISED** 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하기 전에 발생 해야 합니다.  
  
- **WSAENETDOWN** The Windows 소켓 구현이 네트워크 하위 시스템의 실패 했음을 감지 합니다.  
  
- **WSAEINVAL** `nHow` 올바르지 않습니다.  
  
- **WSAEINPROGRESS** 차단 Windows 소켓 작업이 진행 중입니다.  
  
- **WSAENOTCONN** 소켓이 연결 되지 않은 ( **SOCK_STREAM** 만).  
  
- **WSAENOTSOCK** 설명자 소켓 아닙니다.  
  
### <a name="remarks"></a>주의  
 `ShutDown`수신, 전송, 또는 둘 다 사용 하지 않도록 설정 하는 소켓의 모든 형식에 대해 사용 됩니다. 경우 `nHow` 가 0 이므로에 후속 수신 소켓을 사용할 수 없습니다. 이 하위 프로토콜 계층에 영향을 주지 않습니다.  
  
 에 대 한 전송 프로토콜 (TCP Control), TCP 창 변경 되지 않은 들어오는 유지 되며 데이터가 창 가득 찰 때까지 (하지만 승인 하지) 허용 합니다. 에 대 한 사용자 데이터 그램 프로토콜 (UDP), 들어오는 데이터 그램은 수락 및 큐에 대기 합니다. 없는 경우에는 ICMP 패킷은 보내 오류가 생성 됩니다. 경우 `nHow` 는 1, 후속 보냅니다 허용 되지 않습니다. TCP 소켓에 대 한 한 FIN 전송 됩니다. 설정 `nHow` 2 모두 사용 하지 않도록 설정 하 고 위에 설명 된 대로 수신 합니다.  
  
 `ShutDown` 않습니다 하지 close 소켓과 소켓에 연결 된 리소스가 해제 되지 것입니다 될 때까지 **닫습니다** 호출 됩니다. 응용 프로그램이 종료 된 후에 소켓을 다시 사용할 수 있는 것에 있어서는 안 됩니다. 특히, Windows 소켓 구현이 필요가 없습니다의 사용을 지원 **연결** 이러한 소켓에 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CAsyncSocket::OnReceive](#onreceive)합니다.  
  
##  <a name="socket"></a>CASyncSocket::Socket  
 Socket 핸들을 할당합니다.  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSocketType`  
 지정 `SOCK_STREAM` 또는 `SOCK_DGRAM`합니다.  
  
 `lEvent`  
 응용 프로그램은 관심 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.  
  
- `FD_READ`: 읽을 준비 상태에 대 한 알림을 수신 하려고 합니다.  
  
- `FD_WRITE`: 쓰기를 위한 준비에 대 한 알림을 수신 하려고 합니다.  
  
- `FD_OOB`: 밴드의 범위를 벗어난 데이터에 대 한 알림을 수신 하려고 합니다.  
  
- `FD_ACCEPT`: 들어오는 연결에 대 한 알림을 수신 하려고 합니다.  
  
- `FD_CONNECT`: 완료 된 연결에 대 한 알림을 수신 하려고 합니다.  
  
- `FD_CLOSE`: 소켓 닫기를 처리에 대 한 알림을 수신 하려고 합니다.  
  
 `nProtocolType`  
 표시 된 주소 패밀리에 해당 되는 소켓 함께 사용 되는 프로토콜입니다.  
  
 `nAddressFormat`  
 제품군 사양이 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`를 반환하고 실패하면 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 소켓 핸들을 할당합니다. 호출 하지 않습니다 [CAsyncSocket::Bind](#bind) 소켓을 바인딩하지 지정된 된 주소에 호출 해야 하므로 `Bind` 나중 소켓에 바인딩할 지정된 된 주소입니다. 사용할 수 있습니다 [CAsyncSocket::SetSockOpt](#setsockopt) 연결 되기 전에 소켓 옵션을 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSocket 클래스](../../mfc/reference/csocket-class.md)   
 [CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)

