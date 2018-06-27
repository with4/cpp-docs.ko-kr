---
title: 슬라이더 알림 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c383458905d16dda935254e56a5aa9f56a153e83
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956163"
---
# <a name="slider-notification-messages"></a>슬라이더 알림 메시지
슬라이더 컨트롤에는 부모 슬라이더 컨트롤의 방향에 따라 WM_HSCROLL 또는 WM_VSCROLL 메시지를 전송 하 여 사용자 작업의 부모 창을 알립니다. 이러한 메시지를 처리 하려면 부모 창에 WM_HSCROLL 및 WM_VSCROLL 메시지에 대 한 처리기를 추가 합니다. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) 및 [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) 알림 코드, 슬라이더, 및에 대 한 포인터의 위치 전달 될 멤버 함수는 [CSliderCtrl](../mfc/reference/csliderctrl-class.md) 개체입니다. 형식의 포인터는 `CScrollBar *` 가리키도록 하는 경우에는 `CSliderCtrl` 개체입니다. 슬라이더 컨트롤을 조작 하는 경우이 포인터 형식을 캐스팅 해야 할 수 있습니다.  
  
 스크롤 막대를 알림 코드를 사용 하는 대신 슬라이더 컨트롤 알림 코드의 다른 집합을 보냅니다. 슬라이더 컨트롤 사용자가 키보드를 사용 하 여 슬라이더 컨트롤과 상호 작용할 때에 TB_BOTTOM, TB_LINEDOWN, TB_LINEUP, 및 TB_TOP 알림 코드를 보냅니다. TB_THUMBPOSITION 및 TB_THUMBTRACK 알림 메시지는 사용자가 마우스를 사용 하는 경우에 전송 됩니다. 두 경우 모두 TB_ENDTRACK, TB_PAGEDOWN, 및 TB_PAGEUP 알림 코드 전송 됩니다.  
  
 다음 표는 슬라이더 컨트롤 알림 메시지 및 알림 메시지를 발생 시킨 이벤트 (마우스 이벤트 또는 가상 키 코드). (표준 가상 키 코드 목록이 Winuser.h 참조).  
  
|알림 메시지|알림을 보낼 유발 하는 이벤트|  
|--------------------------|-------------------------------------------|  
|TB_BOTTOM|VK_END|  
|TB_ENDTRACK|WM_KEYUP (사용자는 관련 가상 키 코드를 전송 하는 키를 출시 하는 데 사용)|  
|TB_LINEDOWN|VK_RIGHT 또는 VK_DOWN|  
|TB_LINEUP|VK_LEFT 또는 VK_UP|  
|TB_PAGEDOWN|VK_NEXT (사용자 아래에 또는 슬라이더의 오른쪽에 있는 채널을 클릭 하는 데 사용)|  
|TB_PAGEUP|VK_PRIOR (사용자는 채널을 위 또는 왼쪽의 슬라이더를 클릭 하는 데 사용)|  
|TB_THUMBPOSITION|WM_LBUTTONUP 다음 TB_THUMBTRACK 알림 메시지|  
|TB_THUMBTRACK|슬라이더를 이동 (사용자는 슬라이더를 끌어서)|  
|TB_TOP|VK_HOME|  
  
## <a name="see-also"></a>참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

