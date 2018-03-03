---
title: "메시지 보내기 및 받기 | Microsoft Docs"
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
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c587e3b84ae7afd7869a5c1405d8ddc4ab417b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="message-sending-and-receiving"></a>메시지 보내기 및 받기
프로세스 및 프레임 워크의 응답의 송신 부분을 고려 합니다.  
  
 대부분의 메시지 프로그램과 사용자 상호 작용으로 발생 합니다. 메뉴 항목 또는 도구 모음 단추에서 마우스 클릭 하거나 액셀러레이터 키 명령이 생성 됩니다. 또한 사용자 예를 들어 여 Windows 메시지를 생성 이동 하거나 창 크기를 조정 합니다. 다른 Windows 메시지가 windows와 가져오기 또는 포커스를 손실 등 프로그램 시작 또는 종료와 같은 이벤트가 발생할 때 전송 됩니다. 컨트롤 알림 메시지는 마우스 클릭 또는 대화 상자에서 단추 또는 목록 상자 컨트롤 같은 컨트롤을 다른 사용자 상호 작용에 의해 생성 됩니다.  
  
 **실행** 클래스의 멤버 함수 `CWinApp` 메시지를 검색 하 고 적절 한 창에 디스패치합니다. 대부분의 명령 메시지는 응용 프로그램의 주 프레임 창에 전송 됩니다. `WindowProc` 메시지 클래스 라이브러리 gets에서 미리 정의 하 고 수신 되는 메시지의 범주에 따라 서로 다르게 라우팅합니다.  
  
 프로세스의 수신 부분을 알아보겠습니다.  
  
 메시지의 초기 수신기 window 개체 여야 합니다. 일반적으로 Windows 메시지는 해당 window 개체를 직접 처리 합니다. 일반적으로 응용 프로그램의 주 프레임 창에서 발생 하는 명령 메시지에 설명 된 명령 대상 체인에 라우트되지 [명령 라우팅](../mfc/command-routing.md)합니다.  
  
 메시지 또는 명령을 받을 수 있는 각 개체에는 메시지가 자동으로 메시지 또는 처리기의 이름으로 명령 쌍을 매핑합니다.  
  
 명령 대상 개체는 메시지 또는 명령을 받을 경우 일치 하는 항목에 대 한 자신의 메시지 맵을 검색 합니다. 메시지에 대 한 처리기를 찾으면 해당 처리기를 호출 합니다. 메시지 맵을 검색 하는 방법에 대 한 자세한 내용은 참조 [어떻게의 프레임 워크 검색 메시지 맵](../mfc/how-the-framework-searches-message-maps.md)합니다. 그림을 다시 참조 [프레임 워크의 명령](../mfc/user-interface-objects-and-command-ids.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

