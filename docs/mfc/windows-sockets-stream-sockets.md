---
title: 'Windows 소켓: 스트림 소켓 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5499395e517f056ffb224c22c888a3cc0382133
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-stream-sockets"></a>Windows 소켓: 스트림 소켓
이 문서에서는 스트림 소켓 사용할 수 있는 두 개의 Windows 소켓 유형 중 하나를 설명 합니다. (다른 유형이 고 [데이터 그램 소켓](../mfc/windows-sockets-datagram-sockets.md).)  
  
 스트림 소켓 레코드 경계 없이 데이터 흐름에 대 한 제공: 양방향 바이트 스트림을 (응용 프로그램은 전이중: 것 수 모두 송수신 소켓을 통해). 스트림은 의존할 수 순차적 이며 중복 데이터를 제공 합니다. ("Sequenced" 의미 패킷이 보낸 순서 대로 배달 됩니다. "중복" 의미 특정 패킷의 한 번만 얻을 수 있습니다.) 스트림에 메시지를 받았음을 보장 하 고은 많은 양의 데이터 처리에 적합 합니다.  
  
 네트워크 전송 계층은 나눌 수도 데이터를 적절 한 크기의 패킷을 그룹화 있습니다. `CSocket` 클래스에서 처리 압축을 풀고 있습니다.  
  
 스트림 기반 연결을 명시적으로: 소켓 B;에 대 한 연결을 요청 하는 소켓 A 소켓 B 수락 하거나 연결 요청을 거부 합니다.  
  
 전화 통화 스트림에 대 한 좋은 예를 들어를 제공합니다. 정상적인 상황에서는 수신 파티에서 중복 되거나 손실 없이 말, 있는지 순서로 말하는 수신 합니다. 스트림 소켓을 적절 한 등의 프로토콜 FTP (파일 전송)는 현재 전송 ASCII 또는 임의 크기의 이진 파일을 용이 하 게 구현에 대 한 예를 들어 있습니다.  
  
 스트림 소켓은 시점과 데이터 크기가 큰 데이터 도착 하도록 보장 되어야 하는 경우 데이터 그램 소켓 것이 좋습니다. 스트림 소켓에 대 한 자세한 내용은 Windows Sockets 사양을 참조 하십시오. 사양 Windows SDK에서 제공 됩니다.  
  
 스트림 소켓을 사용 하 여 보다 상위 때문에 네트워크에서 받은 모든 소켓으로 브로드캐스트에 대 한 데이터 그램 소켓을 사용 하도록 설계 된 응용 프로그램에 수 있습니다.  
  
-   브로드캐스트 모델 네트워크 서비스 장애 유발 (또는 "스톰") 문제가 될 수 있습니다.  
  
-   적용 되는 클라이언트 서버 모델을 보다 효율적입니다.  
  
-   스트림 모델 데이터 그램 모델 하지 않는 신뢰할 수 있는 데이터 전송을 제공 합니다.  
  
-   최종 모델에서는 CArchive CSocket 클래스에는 해당 클래스 소켓 응용 프로그램에서는 ANSI와 유니코드 간의 통신 하는 기능 활용 합니다.  
  
    > [!NOTE]
    >  클래스를 사용 하는 경우 `CSocket`, 스트림을 사용 해야 합니다. 소켓 형식을로 지정 하면 MFC 어설션이 실패 **SOCK_DGRAM**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)

