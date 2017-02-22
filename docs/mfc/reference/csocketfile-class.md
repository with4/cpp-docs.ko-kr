---
title: "CSocketFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archives [C++], 네트워크"
  - "CSocketFile class"
  - "networks [C++], archive"
  - "networks [C++], serializing to"
  - "serialization[C++], 네트워크"
  - "SOCKET handle"
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CSocketFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A `CFile` 송수신 데이터 네트워크를 통해 Windows 소켓을 사용 하는 개체입니다.  
  
## 구문  
  
```  
class CSocketFile : public CFile  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSocketFile::CSocketFile](../Topic/CSocketFile::CSocketFile.md)|`CSocketFile` 개체를 생성합니다.|  
  
## 설명  
 연결할 수는 `CSocketFile` 개체는 `CSocket` 이 목적에 대 한 개체.  또한 가능한 한 연결, 일반적으로 `CSocketFile` 개체는 `CArchive` 단순화 MFC serialization을 사용 하 여 데이터를 송수신 하는 개체.  
  
 \(보내기\)의 데이터를 serialize 하려면 호출 보관에 삽입 `CSocketFile` 멤버 함수에 데이터를 쓸 수 있는 `CSocket` 개체.  역직렬화 할 \(수신\) 보관 파일에서 추출할 데이터를.  이렇게 아카이브를 호출 하면 `CSocketFile` 멤버 함수에서 데이터를 읽을 수 있는 `CSocket` 개체.  
  
> [!TIP]
>  사용 하는 것 외에도 `CSocketFile` 와 수 여기에 설명 된 대로 독립 실행형 파일 개체로 사용 하 여 수 `CFile`, 해당 기본 클래스.  또한 사용할 수 있습니다 `CSocketFile` 모든 보관 기반 MFC serialization 함수를 사용 합니다.  때문에 `CSocketFile` 모두 지원 `CFile`의 기능을 일부 기본 MFC serialize 함수는 호환 되지 않습니다 `CSocketFile`.  특히 발생의 `CEditView` 클래스입니다.  Serialize 하려고 합니다 `CEditView` 통해 데이터는 `CArchive` 개체를 연결 하는 `CSocketFile` 개체를 사용 하 여 `CEditView::SerializeRaw`. 사용  **CEditView::Serialize** 대신 합니다.  `SerializeRaw` 함수 같은 함수에 파일 개체를 필요로 `Seek`, 해당 `CSocketFile` 있지 않습니다.  
  
 사용 하는 경우 `CArchive` 와 `CSocketFile` 및 `CSocket`, 잠길 수 있습니다 위치  **CSocket::Receive** 루프를 입력 \(여  **PumpMessages\(FD\_READ\)**\) 바이트 요청 된 시간 동안 대기 합니다.  Windows 소켓 마스킹해야 알림 당 하나의 recv 호출을 허용 하기 때문입니다 있지만 `CSocketFile` 및 `CSocket` 마스킹해야 당 여러 recv 호출을 허용 합니다.  읽을 데이터가 없는 경우를 마스킹해야 표시 되 면 응용 프로그램이 정지 합니다.  다른 마스킹해야 되지 않으면 소켓을 통해 통신 응용 프로그램을 중지 합니다.  
  
 다음과 같은 방법으로이 문제를 해결할 수 있습니다.  에 `OnReceive` 메서드를 호출 하면 소켓 클래스의  **CAsyncSocket::IOCtl \(FIONREAD,...\)** 를 호출 하기 전에 `Serialize` 소켓에서 읽을 수 있도록 예상된 데이터 하나의 TCP 패킷 \(네트워크 미디어, 일반적으로 최소한 1096 바이트의 최대 전송 단위\) 크기를 초과 하면 메시지 클래스의 메서드.  사용할 수 있는 데이터의 크기 보다 작으면 받을 다음 읽기 작업을 시작 하 고 모든 데이터를 기다립니다.  
  
 다음 예제에서는 `m_dwExpected` 의 대략적인 개수를 받으려는 바이트입니다.  다른 곳에서 코드에서 선언할 것으로 간주 됩니다.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/CPP/csocketfile-class_1.cpp)]  
  
 자세한 내용은  [mfc에서 Windows 소켓](../../mfc/windows-sockets-in-mfc.md),  [Windows 소켓: 소켓을 사용 하 여 보관소](../../mfc/windows-sockets-using-sockets-with-archives.md)과  [Windows 소켓 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## 요구 사항  
 **헤더:**  afxsock.h  
  
## 참고 항목  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)