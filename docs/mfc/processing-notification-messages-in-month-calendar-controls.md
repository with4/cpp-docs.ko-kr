---
title: 달력의 컨트롤에서에서 알림 메시지 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26b4d73284b0cff362ba16248e0906b76c7f52a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>MonthCalendar 컨트롤에서 알림 메시지 처리
사용자가 컨트롤 (날짜를 선택 및/또는 다른 달 보기), month calendar 컨트롤 상호 작용 하는 대로 (`CMonthCalCtrl`)를 해당 부모 창 알림 메시지를 전송 합니다. 일반적으로 뷰 또는 대화 상자 개체입니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 볼 수는 새로운 달을 선택, 강조 해야 하는 날짜 집합을 제공할 수 있습니다.  
  
 속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.  
  
 다음 목록에는 달력 컨트롤에서 전송 하는 다양 한 알림에 대해 설명 합니다.  
  
-   **MCN_GETDAYSTATE** 굵게 표시 합니다 (일)에 대 한 정보를 요청 합니다. 이 알림 메시지 처리에 대 한 정보를 참조 하십시오. [Monthcalendar 컨트롤의 일 상태 설정](../mfc/setting-the-day-state-of-a-month-calendar-control.md)합니다.  
  
-   **MCN_SELCHANGE** 부모 선택 된 날짜 또는 날짜의 범위 변경 되었음을 알립니다.  
  
-   **MCN_SELECT** 명시적으로 날짜 선택 된 내용이 부모에 알립니다.  
  
## <a name="see-also"></a>참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

