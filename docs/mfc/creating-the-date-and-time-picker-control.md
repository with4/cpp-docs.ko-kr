---
title: "날짜 및 시간 선택 컨트롤 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc83daa0c009f997992e32165c1000d89a17aa98
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤 만들기
날짜 및 시간 선택 컨트롤의 인스턴스가 만들어지는 방법을 대화 상자에서 컨트롤 사용 또는 비 모달 창에서 만드는 인지에 따라 달라 집니다.  
  
### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl 대화 상자에서 직접 사용 하려면  
  
1.  대화 상자 편집기에서 대화 상자 템플릿 리소스에 날짜 및 시간 선택 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.  
  
2.  날짜 및 시간 선택 컨트롤의 속성 대화 상자를 사용 하 여 필요한 스타일을 지정 합니다.  
  
3.  사용 하 여는 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) 컨트롤 속성을 사용 합니다. 이 멤버를 사용하여 `CDateTimeCtrl` 멤버 함수를 호출할 수 있습니다.  
  
4.  속성 창을 사용 하 여 모든 날짜 시간 선택 컨트롤에 대 한 대화 상자 클래스의 처리기 함수를 매핑할 [알림](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) 처리 해야 하는 메시지 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 설정에 대 한 추가 스타일의 `CDateTimeCtrl` 개체입니다.  
  
### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>CDateTimeCtrl 비 모달 창에서 사용 하려면  
  
1.  뷰 또는 창 클래스에서 컨트롤을 선언 합니다.  
  
2.  컨트롤의 호출 [만들기](../mfc/reference/ctabctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)부모 창의 만큼, [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (인 경우 컨트롤을 서브클래싱하). 컨트롤의 스타일을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

