---
title: 'Windows 소켓: 포트 및 소켓 주소 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ea9b8a39de8d36ecb621164d98e072a4041211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows 소켓: 포트 및 소켓 주소
용어 "port" 및 "address"로 Windows 소켓으로 사용 되는이 문서에 설명 합니다.  
  
##  <a name="_core_port"></a> 포트  
 포트는 서비스를 제공할 수 있는 고유한 프로세스를 식별 합니다. 현재 컨텍스트에서 포트는 Windows 소켓을 지 원하는 응용 프로그램에 연결 합니다. 컴퓨터에서 동시에 실행 하는 둘 이상의 Windows 소켓 응용 프로그램을 가질 수 있도록 각 Windows 소켓 응용 프로그램을 고유 하 게 식별 하는 개념은입니다.  
  
 특정 포트 FTP와 같은 일반적인 서비스를 위해 예약 됩니다. 이러한 종류의 서비스를 제공 하는 경우가 아니면 이러한 포트를 사용 하지 않아야 합니다. Windows 소켓 사양을 이러한 예약 된 포트에 자세히 설명 합니다. WINSOCK 파일입니다. H도 나열 됩니다.  
  
 Windows 소켓 DLL에서 사용 가능한 포트를 선택 하도록 포트 값으로 0을 전달 합니다. MFC는 10 진수 1024 보다 큰 포트 값을 선택합니다. MFC를 호출 하 여 선택 된 포트 값을 검색할 수는 [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) 멤버 함수입니다.  
  
##  <a name="_core_socket_address"></a> 소켓 주소  
 각 소켓 개체는 네트워크에서 IP (인터넷 프로토콜) 주소와 연결 합니다. 일반적으로 주소는 "형식인"와 같은 컴퓨터 이름 또는 "128.56.22.8" 등의 점으로 구분 된 번호입니다.  
  
 소켓을 만들지 검색할 때 일반적으로 않아도 고유한 주소를 지정 합니다.  
  
> [!NOTE]
>  컴퓨터에 네트워크 카드가 여러 개 (또는 이러한 컴퓨터에서 응용 프로그램 실행 될 수도 있습니다) 수입니다. 다른 네트워크를 나타내는입니다. 이 경우 소켓 ´ ֲ 네트워크 카드를 지정 하는 주소를 지정 해야 합니다. 이 고급 사용 방법 및 이식성 문제가 발생할 수 있습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

