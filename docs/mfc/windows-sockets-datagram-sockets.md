---
title: "Windows 소켓: 데이터 그램 소켓 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8c19280645edad0d449708434ebbc0ee646e981
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-datagram-sockets"></a>Windows 소켓: 데이터그램 소켓
이 문서에서는 사용할 수 있는 두 개의 Windows 소켓 유형 중 하나는 데이터 그램 소켓을 설명 합니다. (다른 유형이 고 [스트림 소켓](../mfc/windows-sockets-stream-sockets.md).)  
  
 데이터 그램 소켓 sequenced 하거나 중복 보장 되지 않는 양방향 데이터 흐름을 지원 합니다. 데이터 그램도 아닐 수 신뢰할 수 없습니다. 도착 하는 데 실패할 수 있습니다. 데이터 그램 데이터 중복 될 수 및 잘못 된 순서로 도착할 수 있습니다 하지만 기록 데이터의에서 경계를 레코드가 수신기의 내부 크기 제한 보다 더 작은 지으로 유지 됩니다. 시퀀싱 및 안정성 관리 책임이 있습니다. (안정성으로 로컬 영역 네트워크 [LAN]에서 향상 될 수 있지만 온 광역 덜 [WAN] 인터넷과 같은 네트워크).  
  
 즉, 명시적에 연결 되지 않으면, 데이터 그램은 "연결" 됩니다. 지정된 된 소켓 데이터 그램 메시지를 보내기 및 지정된 된 소켓에서 메시지를 받을 수 있습니다.  
  
 데이터 그램 소켓의 예는 동기화 하는 네트워크의 시스템 시계를 보관 하는 응용 프로그램. 일부 설정에서 데이터 그램 소켓의 추가 기능 들: 많은 수의 네트워크 주소에 메시지 브로드캐스트 합니다.  
  
 데이터 그램 소켓은 레코드 기반 데이터에 대 한 스트림 소켓 보다 좋습니다. 데이터 그램 소켓에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows 소켓 사양을 참조 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)

