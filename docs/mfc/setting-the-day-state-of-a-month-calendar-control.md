---
title: 달력 컨트롤의 한 월의 일 상태 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 611397a329e177689a7bd8386963ea1c29ce9e5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380801"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>MonthCalendar 컨트롤의 일 상태 설정
Monthcalendar 컨트롤의 특성 하나 라고 하는 컨트롤의 일 상태 각 날짜의 월에 대 한 정보를 저장 하는 기능입니다. 이 정보는 현재 표시 된 월에 대 한 특정 날짜를 강조 하기 위해 사용 됩니다.  
  
> [!NOTE]
>  `CMonthCalCtrl` 개체 있어야는 **MCS_DAYSTATE** 스타일 일 상태 정보를 표시 합니다.  
  
 일 상태 정보를 32 비트 데이터 형식으로 표현 됩니다 **MONTHDAYSTATE**합니다. 각 비트를 **MONTHDAYSTATE** 비트 필드 (1-31) 하루에 한 달의 상태를 나타냅니다. 비트가 설정 되 면 해당 요일이 표시 됩니다 굵게; 그렇지 않은 경우와 없는 강조 표시 됩니다.  
  
 Monthcalendar 컨트롤의 일 상태 설정 하기 위한 두 가지가: 명시적으로 호출 하 여 [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) 또는 처리 하 여는 **MCN_GETDAYSTATE** 알림 메시지입니다.  
  
## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지를 처리합니다.  
 **MCN_GETDAYSTATE** 표시 개월 내에 있는 일을 표시 하는 방법을 결정 하는 컨트롤에서 메시지가 보내집니다.  
  
> [!NOTE]
>  컨트롤에는 이전 및 다음 달의 표시 된 달에 대해 캐시 하기 때문에 새로운 달을 선택 될 때마다이 알림을 받습니다.  
  
 일 상태 정보 되 고 몇 개월 수에 대 한 요청 배열을 초기화할 결정 해야이 메시지를 올바르게 처리 하려면 **MONTHDAYSTATE** 적절 한 값과 관련 된 구조체 멤버 초기화를 사용 하 여 구조 새 정보입니다. 다음 절차에서는 필요한 단계를 자세히 보여 주는 있다고 가정는 `CMonthCalCtrl` 라는 개체 `m_monthcal` 및 배열을 **MONTHDAYSTATE** 개체 `mdState`합니다.  
  
#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지를 처리 하려면  
  
1.  에 대 한 알림 처리기를 추가 속성 창을 사용 하는 **MCN_GETDAYSTATE** 에 메시지는 `m_monthcal` 개체 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
2.  처리기의 본문에 다음 코드를 추가 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     이 예제에서는 변환는 `pNMHDR` 적절 한 형식에 대 한 포인터는 다음 몇 달의 정보를 요청 하는 결정 (`pDayState->cDayState`). 매월 현재 비트 필드에 대 한 (`pDayState->prgDayState[i]`)은 0이 되 고 그런 다음 필요한으로 초기화 날짜 설정 됩니다 (이 경우 각 월의 15 일)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

