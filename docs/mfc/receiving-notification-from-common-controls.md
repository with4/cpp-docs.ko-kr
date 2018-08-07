---
title: 공용 컨트롤에서 알림 받기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80fefde054ed411dcb30836b2b89cef89cc54e64
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928796"
---
# <a name="receiving-notification-from-common-controls"></a>공용 컨트롤에서 알림 받기
공용 컨트롤은 컨트롤에는 사용자의 입력 등의 이벤트 발생 하는 경우 부모 창에 알림 메시지를 전송 하는 자식 창입니다.  
  
 응용 프로그램이 취할 조치는 사용자가을 확인 하기 위해 이러한 알림 메시지에 의존 합니다. 가장 일반적인 컨트롤 WM_NOTIFY 메시지도 알림 메시지를 보냅니다. Windows 컨트롤 WM_COMMAND 메시지도 대부분의 알림 메시지를 보냅니다. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) WM_NOTIFY 메시지에 대 한 처리기입니다. 와 마찬가지로 `CWnd::OnCommand`, 구현의 `OnNotify` 알림 메시지를 디스패치합니다 `OnCmdMsg` 의 메시지 맵 처리에 대 한 합니다. 알림 처리에 대 한 메시지 맵 항목이 ON_NOTIFY 있습니다. 자세한 내용은 참조 [기술 참고 61: ON_NOTIFY 및 WM_NOTIFY 메시지](../mfc/tn061-on-notify-and-wm-notify-messages.md)합니다.  
  
 파생된 클래스에서 "메시지 리플렉션 합니다."를 사용 하 여 알림 메시지를 처리할 수는 또는 자세한 내용은 참조 [Technical Note 62: Windows 컨트롤에 대 한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)합니다.  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>알림 메시지의 커서 위치를 검색합니다.  
 경우에 따라 공용 컨트롤에서 특정 알림 메시지를 받을 때 커서의 현재 위치를 결정 하는 것이 유용 합니다. 예를 들어, 공용 컨트롤 NM_RCLICK 알림 메시지를 받을 때 현재 커서 위치를 결정 하는 것이 도움이 됩니다.  
  
 이를 위해 호출 하 여 간단한 방법은 `CWnd::GetCurrentMessage`합니다. 그러나이 메서드는 메시지를 보낸 시간에 커서 위치만 검색 했습니다. 커서 이동 했거나 호출 해야 메시지를 보낸 후 때문에 `CWnd::GetCursorPos` 현재 커서 위치를 가져올 수 있습니다.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` 메시지 처리기 내에서 호출 해야 합니다.  
  
 (이 예에서는 NM_RCLICK)에서 알림 메시지 처리기의 본문에 다음 코드를 추가 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 마우스 커서 위치에 저장 됩니다는 시점에서 `cursorPos` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)

