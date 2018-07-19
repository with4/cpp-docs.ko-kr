---
title: 'Windows 소켓: 소켓 클래스에서 파생 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76ccb2ec126ae57e39b1a4fab3a0bff82a353d71
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953764"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows 소켓: 소켓 클래스에서 파생시키기
이 문서에서는 설명의 일부 기능은 소켓 클래스 중 하나에서 고유한 클래스를 파생 하 여 얻을 수 있습니다.  
  
 사용자 고유의 소켓 클래스를 파생 될 수 있습니다 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 또는 [CSocket](../mfc/reference/csocket-class.md) 사용자 고유의 기능을 추가 합니다. 특히 이러한 클래스는 재정의할 수 있는 가상 멤버 함수의 수를 제공 합니다. 이러한 함수에 포함 [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), 및 [OnClose](../mfc/reference/casyncsocket-class.md#onclose)합니다. 네트워크 이벤트가 발생할 때 제공 되는 알림 활용 하기 위해 파생된 소켓 클래스에서 함수를 재정의할 수 있습니다. 프레임 워크 알려 주기 위해 데이터를 받지 같은 중요 한 소켓 이벤트 읽기를 시작할 수 있는 이러한 알림 콜백 함수를 호출 합니다. 알림 함수에 대 한 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md)합니다.  
  
 또한 클래스 `CSocket` 제공는 [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) 멤버 함수 (고급는 재정의 가능한). MFC는 소켓은 Windows 기반 메시지를 펌프 하는 동안이 함수를 호출 합니다. 재정의할 수 `OnMessagePending` 를 Windows에서 특정 메시지를 검색 하 고 응답할 수 있습니다.  
  
 기본 버전 `OnMessagePending` 클래스에 제공 된 `CSocket` 차단 호출이 완료 되기를 기다리는 동안 WM_PAINT 메시지에 대 한 메시지 큐를 검사 합니다. 디스플레이 품질 향상 그리기 메시지를 발송 합니다. 필요한 작업을 수행 하는 것 외 들 함수를 재정의 하는 한 가지 방법은 직접 합니다. 또 다른 예로,으로 사용 하 여 `OnMessagePending` 다음 작업에 대 한 합니다. 네트워크 트랜잭션이 완료 되기를 기다리는 동안 모덜리스 대화 상자를 표시 한다고 가정 합니다. 대화 상자에는 사용자 차단 트랜잭션이 시간이 오래 걸리는 취소 하는 데 사용할 수 있는 취소 단추가 있습니다. 프로그램 `OnMessagePending` 재정의이 모덜리스 대화 상자와 관련 된 메시지를 펌프 될 수 있습니다.  
  
 사용자 `OnMessagePending` 재정의 반환 **TRUE** 의 기본 클래스 버전에 대 한 호출에서 반환 된 값 또는 `OnMessagePending`합니다. 여전히 원하는 작업을 수행 하는 경우 기본 클래스 버전을 호출 합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)  
  
-   [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

