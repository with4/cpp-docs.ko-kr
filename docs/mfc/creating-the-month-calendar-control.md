---
title: 컨트롤 Monthcalendar 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5cb58cfbecd03964963814081c2f0039c0752c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-month-calendar-control"></a>MonthCalendar 컨트롤 만들기
달력 컨트롤을 만드는 방법은 대화 상자에서 컨트롤을 사용 중인지 또는 비모달 창에서 만드는지에 따라 달라집니다.  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>대화 상자에서 CMonthCalCtrl을 직접 사용하려면  
  
1.  대화 상자 편집기에서 달력 컨트롤을 대화 상자 템플릿 리소스에 추가합니다. 해당 컨트롤 ID를 지정합니다.  
  
2.  달력 컨트롤의 속성 대화 상자를 사용해서 필요한 스타일을 지정합니다.  
  
3.  사용 하 여는 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) 컨트롤 속성을 사용 합니다. 이 멤버를 사용하여 `CMonthCalCtrl` 멤버 함수를 호출할 수 있습니다.  
  
4.  모든 달력 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수에 매핑할 속성 창에서 처리 해야 하는 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 설정에 대 한 추가 스타일의 `CMonthCalCtrl` 개체입니다.  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>비모달 창에서 CMonthCalCtrl을 사용하려면  
  
1.  뷰 또는 창 클래스에서 컨트롤을 정의합니다.  
  
2.  컨트롤의 호출 [만들기](../mfc/reference/cmonthcalctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)부모 창의 만큼, [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (인 경우 컨트롤을 서브클래싱하). 컨트롤의 스타일을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

