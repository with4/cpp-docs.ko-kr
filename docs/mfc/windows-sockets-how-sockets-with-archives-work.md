---
title: 'Windows 소켓: 아카이브를 함께 사용 하는 소켓 작동 방식 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c03ae586e346be2ba1e7c71475b69318ded0dd18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법
이 문서에서는 설명 어떻게는 [CSocket](../mfc/reference/csocket-class.md) 개체는 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체 및 [CArchive](../mfc/reference/carchive-class.md) 개체는 Windows 통해 데이터 보내기 및 받기 간소화 하기 위해 결합 됩니다 소켓입니다.  
  
 문서 [Windows 소켓: 소켓을 사용 하 여 보관 파일 예제](../mfc/windows-sockets-example-of-sockets-using-archives.md) 표시는 **PacketSerialize** 함수입니다. 보관 개체에는 **PacketSerialize** 예제는 MFC에 전달 되는 보관 개체 처럼 작동 [Serialize](../mfc/reference/cobject-class.md#serialize) 함수입니다. 소켓에 대 한 보관 파일에 연결 되어 있는지 하지 표준 필수 차이점은 [CFile](../mfc/reference/cfile-class.md) (일반적으로 연결 된 개체는 디스크 파일) 아닌 한 `CSocketFile` 개체입니다. 디스크 파일에 연결 하는 대신는 `CSocketFile` 개체에 연결 하는 `CSocket` 개체입니다.  
  
 A `CArchive` 개체 버퍼를 관리 합니다. 저장 (송신) 보관 저장소가 버퍼가 꽉 차면, 연결 된 `CFile` 개체는 버퍼의 내용을 씁니다. 버퍼를 플러시하는 소켓에 연결 하는 보관의 메시지를 보내는 것과 같습니다. 로드 (수신) 보관의 버퍼가 꽉 차면는 `CFile` 버퍼를 다시 사용할 수 있는 될 때까지 개체 읽기를 중지 합니다.  
  
 클래스 `CSocketFile` 에서 파생 `CFile`, 하지만 지원 하지 않습니다 [CFile](../mfc/reference/cfile-class.md) 위치 지정 함수 같은 멤버 함수 (`Seek`, `GetLength`, `SetLength`등), (함수 잠금 `LockRange`, `UnlockRange`), 또는 `GetPosition` 함수입니다. 모든는 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체 작업을 수행 해야 쓰기 또는 읽기에서 연결 된 바이트 시퀀스는 `CSocket` 개체입니다. 파일은 관여 하지 않기 때문에와 같은 작업 `Seek` 및 `GetPosition` 의미가 있습니다. `CSocketFile` 파생 된 `CFile`이므로 이러한 멤버 함수는 모두 상속 일반적으로 것입니다. 이 지원 되지 않는 방지 하기 위해 `CFile` 에서 멤버 함수를 재정의할 `CSocketFile` throw 하는 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 `CSocketFile` 개체 멤버의 함수를 호출 해당 `CSocket` 를 보내거나 받는 데이터 개체입니다.  
  
 다음 그림은 통신의 양쪽 모두에 이러한 개체 간의 관계입니다.  
  
 ![CArchive, CSocketFile 및 CSocket](../mfc/media/vc38ia1.gif "vc38ia1")  
CArchive, CSocketFile 및 CSocket  
  
 복잡성이의 목적은 직접 소켓의 세부 정보를 관리할 필요가 없도록 하기입니다. 소켓, 파일 및 보관을 만들고 보관 파일에 삽입 하거나 보관 파일에서 추출 하 여 송신 또는 수신 데이터를 시작 합니다. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), 및 [CSocket](../mfc/reference/csocket-class.md) 원리를 자세히 파악할수록 세부 사항을 관리 합니다.  
  
 A `CSocket` 개체는 실제로 두 가지 상태 개체: 경우에 따라 비동기 (일반적인 상태) 동기 합니다. 비동기 상태에서 소켓 프레임 워크에서 비동기 알림을 받을 수 있습니다. 그러나 데이터를 보내거나 받는지 작업 도중 소켓 동기 상태가 됩니다. 즉, 소켓이 동기 작업이 완료 될 때까지 비동기 알림을 받습니다. 모드 전환 되기 때문에 다음과 같은 예를 들어 수행할 수 있습니다.  
  
 [!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]  
  
 경우 `CSocket` 구현 되지 않았습니다 두 가지 상태 개체로 수도 이전 알림을 처리 된 동안에 같은 종류의 이벤트에 대 한 추가 알림 없이 자동을 받을 수 있습니다. 예를 들어 발생할 수 있습니다는 `OnReceive` 처리 하는 동안 알림은 `OnReceive`합니다. 위의 코드 조각에서 추출 `str` 보관 파일에서 재귀가 발생할 수 있습니다. 상태, 전환 하 여 `CSocket` 추가 알림 없이 자동 수 없도록 하 여 재귀를 방지 합니다. 일반적인 규칙은 알림 내 알림이 표시 되지 않습니다.  
  
> [!NOTE]
>  A `CSocketFile` 없이 (제한 됨) 파일로 사용할 수도 있습니다는 `CArchive` 개체입니다. 기본적으로는 `CSocketFile` 생성자의 `bArchiveCompatible` 매개 변수는 **TRUE**합니다. 보관 파일에 사용할 파일 개체 임을 지정 합니다. 아카이브 없이 파일 개체를 사용 하려면 전달 **FALSE** 에 `bArchiveCompatible` 매개 변수입니다.  
  
 "보관 호환 되는" 모드로 `CSocketFile` 개체 더 나은 성능을 제공 하 고 "deadlock." 위험이 감소 합니다. 보내는 소켓과 받는 소켓, 서로 대기 중 또는 일반 리소스 대기는 교착 상태가 발생 합니다. 경우 이러한 상황이 발생할 수 있습니다는 `CArchive` 와 협력 하는 개체는 `CSocketFile` 늘어나도 방식으로 `CFile` 개체입니다. 와 `CFile`, 아카이브 요청한 것 보다 적은 바이트를 수신 하는 경우 파일의 끝에 도달 했음을 가정할 수 있습니다. 그러나와 `CSocketFile`, 데이터를 기반으로 하는 메시지 버퍼에는 여러 개의 메시지가 포함 될 수 있습니다, 하므로 요청 된 바이트 수보다 적은지를 받는 파일의 끝을 의미 하지 않습니다. 와 같이이 경우 응용 프로그램 차단 하지 않습니다 `CFile`는 버퍼가 비어 있을 때까지 버퍼에서 메시지를 읽는 계속할 수 있습니다. [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) 함수 `CArchive` 이러한 경우 보관 파일의 버퍼의 상태를 모니터링 하는 데 유용 합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [Cobject:: Serialize](../mfc/reference/cobject-class.md#serialize)

