---
title: MFC의 Windows 소켓 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84fc25ab6515b22fa647b3cc32833c791b59f2b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-in-mfc"></a>MFC의 Windows 소켓
> [!NOTE]
>  MFC Windows 소켓 1을 지원 하지만 지원 하지 않습니다 [Windows 소켓 2](http://msdn.microsoft.com/library/windows/desktop/ms740673)합니다. Windows 소켓 2 먼저 Windows 98와 함께 제공 되 고 Windows 2000에 포함 된 버전입니다.  
  
 MFC는 Windows 소켓, 두 개의 MFC 클래스에 구현으로 네트워크 통신 프로그램을 작성 하기 위한 두 가지 모델을 제공 합니다. 이 문서에서는 이러한 모델을 설명 하 고 자세한 내용은 MFC 소켓 지원. "소켓" 통신의 끝점은: 응용 프로그램이 통신 하는 다른 Windows 소켓 응용 프로그램과 네트워크를 통해 개체입니다.  
  
 Windows 소켓, 소켓 개념에 대 한 설명을 포함 하 여에 대 한 내용은 [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)합니다.  
  
##  <a name="_core_sockets_programming_models"></a> 소켓 프로그래밍 모델  
 프로그래밍 모델 두 MFC Windows 소켓 클래스에서 지원 됩니다.  
  
-   `CAsyncSocket`  
  
     이 클래스는 Windows 소켓 API를 캡슐화합니다. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 는 프로그래머가 사용할 수 있는 네트워크 프로그래밍 및 소켓 API에 직접 프로그래밍의 융통성 있게 하지만 네트워크 이벤트에 대 한 알림을 콜백 함수의 편리를 할 수도 있습니다. 패키지 c + +에서 사용 하기 위해 폼 개체 지향 소켓, 이외으로이 클래스를 제공 하는 유일한 추가적인 추상화는를 콜백으로 특정 소켓 관련 Windows 메시지를 변환 합니다. 자세한 내용은 참조 [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md)합니다.  
  
-   `CSocket`  
  
     이 클래스에서 파생 된 `CAsyncSocket`, 소켓은 MFC 통해 작업에 대 한 상위 수준 추상화를 제공 [CArchive](../mfc/reference/carchive-class.md) 개체입니다. MFC의 파일 serialization 프로토콜을 사용 하 여 유사 크게 보관 된 소켓을 사용 합니다. 이렇게 하면 보다 사용 하기 쉽게는 `CAsyncSocket` 모델입니다. [CSocket](../mfc/reference/csocket-class.md) 많은 멤버 함수에서 상속 `CAsyncSocket` Windows 소켓 Api를 캡슐화 하는, 이러한 함수 중 일부를 사용 하 고 소켓 프로그래밍의 개요를 이해 해야 합니다. 하지만 `CSocket` 원시 API 또는 클래스를 사용 하 여 직접 수행 해야 하는 통신의 여러 측면을 관리 `CAsyncSocket`합니다. 가장 중요 한 점은 `CSocket` (백그라운드 처리와 Windows 메시지의) 차단을 제공의 동기 작업 하는 데 필수적인 `CArchive`합니다.  
  
 만들기 및 사용 하 여 `CSocket` 및 `CAsyncSocket` 개체에서 설명 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../mfc/windows-sockets-using-sockets-with-archives.md) 및 [Windows 소켓: 클래스를 사용 하 여 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)합니다.  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows 소켓 Dll  
 Microsoft Windows 운영 체제에서는 Windows 소켓 동적 연결 라이브러리 (DLL)를 제공합니다. Visual c + +에는 적절 한 헤더 파일, 라이브러리 및 Windows 소켓 사양을 제공합니다.  
  
 Windows 소켓에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)  
  
-   [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>참고 항목  
 [Windows 소켓](../mfc/windows-sockets.md)

