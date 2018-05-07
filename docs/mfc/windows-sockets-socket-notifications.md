---
title: 'Windows 소켓: 소켓 알림 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b51bf2b562f0d4eff5b9cfef557e62f996d53470
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-socket-notifications"></a>Windows 소켓: 소켓 알림
이 문서는 소켓 클래스의 알림 함수를 설명합니다. 이러한 멤버 함수는 프레임 워크는 중요 한 이벤트 소켓 개체에 알리기 위해 호출 하는 콜백 함수입니다. 알림 기능은 다음과 같습니다.  
  
-   [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive):를 호출 하 여 검색에 대 한 버퍼의 데이터는이 소켓에 알립니다. [수신](../mfc/reference/casyncsocket-class.md#receive)합니다.  
  
-   [OnSend](../mfc/reference/casyncsocket-class.md#onsend): 호출 하 여 데이터 보내기 이제 수이 소켓에 알립니다. [보낼](../mfc/reference/casyncsocket-class.md#send)합니다.  
  
-   [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): 호출 하 여 보류 중인 연결 요청 받을 수 있는이 수신 소켓 알립니다 [Accept](../mfc/reference/casyncsocket-class.md#accept)합니다.  
  
-   [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect):이 소켓에 연결 하는 연결 시도 완료 하는 알립니다: 아마도 성공적으로 또는 시스템 오류가 발생 합니다.  
  
-   [OnClose](../mfc/reference/casyncsocket-class.md#onclose):에 연결 된 소켓 닫이 소켓에 알립니다.  
  
    > [!NOTE]
    >  추가 알림 함수는 [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata)합니다. 이 알림은 "아웃 밴드" 보낼 데이터를 보내는 소켓에 수신 소켓을 알려 줍니다. 대역폭을 벗어난 데이터에는 연결 된 스트림 소켓의 각 쌍과 연결 된 논리적으로 독립 채널입니다. 밴드의 범위를 벗어난 채널은 일반적으로 "긴급" 데이터를 보내는 데 사용 됩니다. MFC는 대역폭을 벗어난 데이터를 지원합니다. 고급 클래스와 함께 작업 하는 사용자 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 밴드의 범위를 벗어난 채널이 아니지만 클래스의 사용자가 사용 하 여 [CSocket](../mfc/reference/csocket-class.md) 사용 해서는 안 됩니다. 쉬운 방법이 이러한 데이터를 전달 하기 위한 두 번째 소켓을 만드는 것입니다. 대역폭을 벗어난 데이터에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows 소켓 사양을 참조 하십시오.  
  
 클래스에서 파생 하는 경우 `CAsyncSocket`, 이벤트를 응용 프로그램 네트워크에 대 한 알림 함수를 재정의 해야 합니다. 클래스에서 클래스를 파생 하는 경우 `CSocket`, 관심 있는 알림 함수를 무시할 것인지 사용자 옵션입니다. 사용할 수도 있습니다 `CSocket` 자체는 경우 알림을 함수 기본적으로 아무 작업도 수행 합니다.  
  
 이러한 함수는 재정의할 수 있는 콜백 함수입니다. `CAsyncSocket` 및 `CSocket` 알림, convert 메시지 하지만 사용 하려는 경우 응답 알림을 작동 하는 방법을 구현 해야 합니다. 알림 함수 소켓 데이터를 읽을 수 있는지 여부 등의 관련 이벤트를 알려 줍니다 때 호출 됩니다.  
  
 MFC는 알림을 받을 때 소켓의 동작을 사용자 지정할 수 있도록 알림 함수를 호출 합니다. 예를 들어, 호출할 수 있습니다 **수신** 에서 프로그램 `OnReceive` 알림 기능, 즉 않게 알림을 읽을 데이터를 호출 합니다 **수신** 을 읽을 수 있습니다. 이 방법은 작업은 필요 하지 않은 적합 한 시나리오입니다. 진행률을 추적 하려면 알림 함수를 사용할 수 있습니다 인쇄 **추적** 메시지 및 등입니다.  
  
 소켓 파생된 클래스에서 알림 함수를 재정의 하 고 구현을 제공 하 여 이러한 알림의 이용할 수 있습니다.  
  
 보내거나 받는 데이터를 작업 하는 동안 한 `CSocket` 개체 동기 됩니다. 동기 상태에 있는 동안 다른 소켓을 위한 알림은 현재 소켓은 원하는 알림을 기다리는 동안 대기 합니다. (예: 동안는 **수신** 호출 소켓이 읽기 알림을.) 소켓에서 동기 작업을 완료 하 고 다시 비동기 상태가 다른 소켓 큐에 대기 중인된 알림 수신을 시작할 수 있습니다.  
  
> [!NOTE]
>  `CSocket`, `OnConnect` 알림 함수는 호출 되지 않습니다. 연결에 대 한 호출 **연결**, (성공적으로 또는 오류가) 연결이 완료 되 면 반환 반환 됩니다. MFC 구현 정보는 연결 알림을 처리 하는 방법입니다.  
  
 자세한 내용은 각 알림 기능에 대 한 클래스 아래 함수를 참조 하십시오. `CAsyncSocket` 에 *MFC 참조*합니다. 소스 코드와 MFC 샘플에 대 한 정보에 대 한 참조 [MFC 샘플](../visual-cpp-samples.md)합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)  
  
-   [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

