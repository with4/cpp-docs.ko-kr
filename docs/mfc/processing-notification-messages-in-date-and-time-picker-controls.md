---
title: "알림 메시지 처리 날짜 및 시간 선택 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs: C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 836714f7a7ca17d759d0d71a7cbb30d63fdfaf95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>날짜 및 시간 선택 컨트롤의 알림 메시지 처리
사용자가 조작 된 날짜 및 시간 선택 컨트롤, 컨트롤 (`CDateTimeCtrl`)를 해당 부모 창 알림 메시지를 전송 합니다. 일반적으로 뷰 또는 대화 상자 개체입니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 열 때 포함 된 month calendar 컨트롤을 표시 하 고 날짜 및 시간 선택기는 **DTN_DROPDOWN** 알림이 전송 됩니다.  
  
 속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.  
  
 다음 목록에는 날짜 및 시간 선택 컨트롤에서 전송 하는 다양 한 알림에 대해 설명 합니다.  
  
-   **DTN_DROPDOWN** 포함 된 month calendar 컨트롤 표시 하려고 하는 부모에 알립니다. 이 알림은 전송만 됩니다는 **DTS_UPDOWN** 스타일 설정 되지 않았습니다. 이 알림에 대 한 자세한 내용은 참조 하십시오. [포함 된 Monthcalendar 컨트롤 액세스](../mfc/accessing-the-embedded-month-calendar-control.md)합니다.  
  
-   **DTN_CLOSEUP** 곧 포함 된 month calendar 컨트롤은 부모에 알립니다. 이 알림은 전송만 됩니다는 **DTS_UPDOWN** 스타일 설정 되지 않았습니다.  
  
-   **DTN_DATETIMECHANGE** 컨트롤에서 변경 내용이 발생 하는 부모에 알립니다.  
  
-   **DTN_FORMAT** 콜백 필드에 표시할 텍스트 필요 함을 부모에 알립니다. 이 알림 및 콜백 필드에 대 한 자세한 내용은 참조 하십시오. [날짜 및 시간 선택 컨트롤에서 콜백 필드 사용 하 여](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.  
  
-   **DTN_FORMATQUERY** 콜백 필드에 표시 되는 문자열의 최대 허용 크기를 제공 하는 부모를 요청 합니다. 이 알림 처리를 컨트롤의 디스플레이 내에서 깜빡임 줄이기 항상 올바르게 표시 출력 제어할 수 있습니다. 이 알림에 대 한 자세한 내용은 참조 하십시오. [날짜 및 시간 선택 컨트롤에서 콜백 필드 사용 하 여](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.  
  
-   **DTN_USERSTRING** 는 사용자가 내용을 편집 하는 날짜 및 시간 선택 컨트롤의 부모에 알립니다. 이 알림은 전송만 됩니다는 **DTS_APPCANPARSE** 스타일 설정 되었습니다.  
  
-   **되므로 DTN_WMKEYDOWN** 콜백 필드에 사용자를 입력 하면 부모에 알립니다. 날짜 및 시간 선택 컨트롤에서 콜백이 아닌 필드에 대 한 지원 같은 키보드 응답을 에뮬레이션 하기 위해이 알림을 처리 합니다. 이 알림에 대 한 자세한 내용은 참조 하십시오. [DTP 컨트롤에서 콜백 필드를 지 원하는](http://msdn.microsoft.com/library/windows/desktop/bb761726) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

