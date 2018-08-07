---
title: CSocketFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f1198c85b8366d7dec4d38d002b65468c38347c
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121731"
---
# <a name="csocketfile-class"></a>CSocketFile 클래스
Windows 소켓을 통해 네트워크에서 데이터를 보내고 받는 데 사용되는 `CFile` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|`CSocketFile` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 연결할 수 있습니다는 `CSocketFile` 개체는 `CSocket` 이 용도 대 한 개체입니다. 또한 수 있으며를 연결 하는 일반적으로 `CSocketFile` 개체를 `CArchive` MFC serialization을 사용 하 여 데이터 보내기 및 받기 단순화 하는 개체입니다.  
  
 (송신) 데이터를 직렬화 하는 데에 삽입 될 호출 하는 보관 `CSocketFile` 에 데이터를 기록 하는 멤버 함수는 `CSocket` 개체입니다. Deserialize 하는 데 (수신) 보관 파일에서 추출할 데이터를 합니다. 이 인해 호출 된 보관 `CSocketFile` 에서 데이터를 읽을 멤버 함수는 `CSocket` 개체입니다.  
  
> [!TIP]
>  사용 하 여 외에도 `CSocketFile` 여기 설명 된 대로 사용할 수 있습니다를 독립 실행형 파일 개체로 있는 경우와 마찬가지로 `CFile`, 해당 기본 클래스입니다. 사용할 수도 있습니다 `CSocketFile` 모든 보관 기반 MFC serialization 함수와 함께 합니다. 때문에 `CSocketFile` 의 일부를 지원 하지 않는 `CFile`의 기능을 몇 가지 기본 MFC serialize 함수와 호환 되지 않습니다. `CSocketFile`합니다. 이 특히의 `CEditView` 클래스입니다. Serialize 하려고 하면 `CEditView` 를 통해 데이터는 `CArchive` 개체에 연결 되어는 `CSocketFile` 개체 사용 하 여 `CEditView::SerializeRaw`; 사용 하 여 `CEditView::Serialize` 대신 합니다. `SerializeRaw` 함수에서는 파일 개체와 같은 함수를 `Seek`, 해당 `CSocketFile` 가 없습니다.  
  
 사용 하는 경우 `CArchive` 와 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있습니다 위치 `CSocket::Receive` 루프로 실행 (여 `PumpMessages(FD_READ)`) 기다리는 중 요청 된 바이트의 양입니다. Windows 소켓 작업할 알림 당 하나의 수신 호출을 허용 하기 때문에 이것이 하지만 `CSocketFile` 및 `CSocket` 작업할 당 여러 수신 호출을 허용 합니다. 읽을 데이터가 없는 경우에 작업할을 얻게 하는 경우 응용 프로그램이 중단 됩니다. 다른 작업할 가져오지 응용 프로그램이 소켓을 통해 통신을 중지 합니다.  
  
 다음과 같이이 문제를 해결할 수 있습니다. 에 `OnReceive` 소켓 클래스, 호출의 메서드로 `CAsyncSocket::IOCtl(FIONREAD, ...)` 호출 하기 전에 `Serialize` TCP 패킷 하나의 네트워크 중간 (최대 전송 단위 크기를 초과 하는 소켓에서 읽이 예상된 데이터 메시지 클래스의 메서드 일반적으로 적어도 1096 바이트)입니다. 사용 가능한 데이터의 크기 보다 작은 경우, 모든 데이터를 받아 읽기 작업을 다시 시작 될 때까지 기다립니다.  
  
 다음 예에서 `m_dwExpected` 사용자를 수신 해야 하는 바이트의 대략적인 수입니다. 선언 하 고 다른 곳에서 코드에 가정 됩니다.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 자세한 내용은 참조 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md),으로 [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 `CSocketFile` 개체를 생성합니다.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSocket*  
 소켓에 연결 하는 `CSocketFile` 개체입니다.  
  
 *bArchiveCompatible*  
 파일 개체와 함께 사용할 인지를 지정 된 `CArchive` 개체입니다. 사용 하려는 경우에 FALSE 패스는 `CSocketFile` 독립 실행형와 마찬가지로 독립 실행형 방식에서 개체 `CFile` 특정 제한 사항과 함께 개체입니다. 이 플래그를 변경 방법을 `CArchive` 개체에 연결 된 `CSocketFile` 개체 읽기 위해 버퍼를 관리 합니다.  
  
### <a name="remarks"></a>설명  
 개체의 소멸자가 개체가 범위에서 벗어나거나 삭제 될 때 자체 소켓 개체에서 분리 합니다.  
  
> [!NOTE]
>  A `CSocketFile` 없이 (제한 됨) 파일로 사용할 수도 있습니다는 `CArchive` 개체입니다. 기본적으로는 `CSocketFile` 생성자의 *bArchiveCompatible* 매개 변수는 TRUE입니다. 보관 파일에 사용할 파일 개체 임을 지정 합니다. 아카이브 없이 파일 개체를 사용 하려면 FALSE에 전달 된 *bArchiveCompatible* 매개 변수입니다.  
  
 "보관 호환 되는" 모드로 `CSocketFile` 개체 더 나은 성능을 제공 하 고 "deadlock." 위험이 감소 합니다. 교착 상태는 보내는 소켓과 받는 소켓은 서로 또는 일반 리소스에 대 한 대기 중인 경우 발생 합니다. 경우 이러한 상황이 발생할 수 있습니다는 `CArchive` 와 협력 하는 개체는 `CSocketFile` 늘어나도 방식으로 `CFile` 개체입니다. 와 `CFile`, 아카이브 요청한 것 보다 적은 바이트를 수신 하는 경우 파일의 끝에 도달 했음을 가정할 수 있습니다.  
  
 그러나와 `CSocketFile`, 데이터를 기반으로 하는 메시지 버퍼에는 여러 개의 메시지가 포함 될 수 있습니다, 하므로 요청 된 바이트 수보다 적은지를 받는 파일의 끝을 의미 하지 않습니다. 와 같이이 경우 응용 프로그램 차단 하지 않습니다 `CFile`는 버퍼가 비어 있을 때까지 버퍼에서 메시지를 읽는 계속할 수 있습니다. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) 함수는 이러한 경우 보관 파일의 버퍼의 상태를 모니터링 하는 데 유용 합니다.  
  
 사용에 대 한 자세한 내용은 `CSocketFile`, 문서를 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md) 및 [Windows 소켓: 소켓을 사용 하 여 보관 파일 예제](../../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)   
 [CSocket 클래스](../../mfc/reference/csocket-class.md)
