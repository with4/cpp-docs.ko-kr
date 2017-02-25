---
title: "MonthCalendar 컨트롤 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl 클래스, 만들기"
  - "MonthCalendar 컨트롤"
  - "MonthCalendar 컨트롤, 만들기"
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MonthCalendar 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Month calendar 컨트롤의 인스턴스가 만들어지는 방법은 대화 상자에서 컨트롤을 사용하는지 또는 비대화상자창에서 작성하는지 여부에 따라 달라 집니다.  
  
### 직접 대화상자에서 CMonthCalCtrl를 사용하세요.  
  
1.  대화 상자 편집기에서 Month Calendar 컨트롤을 대화 상자 템플릿 리소스에 추가 합니다.  컨트롤 ID를 지정 합니다.  
  
2.  Month calendar 컨트롤의 속성 대화 상자를 사용하여 필요한 스타일을 지정 합니다.  
  
3.  컨트롤 속성으로 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) 형식의 멤버 변수를 추가하려면[멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 을 사용합니다.  `CMonthCalCtrl` 멤버 함수를 호출하려면 이 멤버를 사용합니다.  
  
4.  사용자가 처리해야하는 모든 달 달력 컨트롤 알림 메시지를 위해 대화 상자 클래스에서 처리기 함수를 매핑하기 위해서는 속성 창을 사용합니다\([함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)을 참조하세요\).  
  
5.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)에서, `CMonthCalCtrl` 개체에 대해 추가적인 스타일을 설정하세요.  
  
### 비 대화상자 창에서 CMonthCalCtrl을 사용  
  
1.  뷰 또는 창 클래스에 컨트롤을 정의 합니다.  
  
2.  컨트롤의 [Create](../Topic/CMonthCalCtrl::Create.md) 멤버 함수를 호출합니다. [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), 부모 창의 [OnCreate](../Topic/CWnd::OnCreate.md) 처리기 함수 \(만약 사용자가 컨트롤을 서브클래싱한다면\)  컨트롤의 스타일을 설정 합니다.  
  
## 참고 항목  
 [CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)