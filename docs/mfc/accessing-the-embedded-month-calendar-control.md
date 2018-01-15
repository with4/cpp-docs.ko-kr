---
title: "Monthcalendar 컨트롤 액세스는 포함 된 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e37d23a7d5d860d55e18f709c873a40d8f24f1c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-the-embedded-month-calendar-control"></a>포함된 MonthCalendar 컨트롤 액세스
포함 된 month calendar 컨트롤 개체에서 액세스할 수는 `CDateTimeCtrl` 을 호출 하 여 개체는 [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) 멤버 함수입니다.  
  
> [!NOTE]
>  날짜 및 시간 선택 컨트롤에 없는 경우에 포함 된 month calendar 컨트롤 사용은 **DTS_UPDOWN** 스타일을 설정 합니다.  
  
 포함 된 컨트롤에 표시 되기 전에 특정 특성을 수정 하려는 경우에 유용 합니다. 이를 위해 처리는 **DTN_DROPDOWN** 알림을 month calendar 컨트롤 검색 (사용 하 여 [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)), 수정 내용을 확인 합니다. 안타깝게도, month calendar 컨트롤 지속 되지 않습니다.  
  
 즉, 사용자가 달력 컨트롤의 표시를 요청 하는 경우 새 month calendar 컨트롤 만들어집니다 (전에 **DTN_DROPDOWN** 알림). 컨트롤이 소멸 될 (후의 **DTN_CLOSEUP** 알림)는 사용자가 해제할 때. 즉, 포함 된 컨트롤 표시 되기 전에 수정 특성이 포함 된 컨트롤은 해제할 때 손실 됩니다.  
  
 다음 예제에 대 한 처리기를 사용 하 여이 절차는 **DTN_DROPDOWN** 알림입니다. Month calendar 컨트롤을 호출 하 여의 배경색을 변경 하는 코드 [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), 회색입니다. 코드는 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 앞서 설명한 것 처럼 month calendar 컨트롤의 속성 수정 사항이 모두 포함 된 컨트롤을 해제 하는 경우 두 가지 예외가 손실 됩니다. 첫 번째 예외 month calendar 컨트롤 색 이미 설명 했습니다. 두 번째 예외 month calendar 컨트롤에 의해 사용 되는 글꼴입니다. 호출 하 여 기본 글꼴을 수정할 수 있습니다 [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), 기존 글꼴의 핸들을 전달 합니다. 다음 예제에서는 (여기서 `m_dtPicker` 는 날짜 및 시간 제어 개체) 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 글꼴 변경, 호출 하 여 `CDateTimeCtrl::SetMonthCalFont`, 새 글꼴에 저장 되 고 다음에 표시 하는 달력을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

