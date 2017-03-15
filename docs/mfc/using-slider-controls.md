---
title: "슬라이더 컨트롤 사용 | Microsoft Docs"
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
  - "CSliderCtrl 클래스, using"
  - "슬라이더 컨트롤"
  - "슬라이더 컨트롤, using"
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 슬라이더 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

슬라이더 컨트롤의 일반적인 사용 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다.  컨트롤ㅇ이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동 생성이 됩니다. \(슬라이더 컨트롤에 해당하는 대화 상자 클래스의[CSliderCtrl](../mfc/reference/csliderctrl-class.md) 멤버를 가져야합니다. \) 대신  [만들기](../Topic/CSliderCtrl::Create.md) 멤버 함수를 사용하여 컨트롤 창의 자식 창으로 만들 수 있습니다.  
  
-   컨트롤에 대한 값을 설정하는 다양한 Set 멤버 함수를 호출합니다.  슬라이더에 대한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위 설정 및 슬라이더 위치 조정 등 설정을 변경합니다.  대화 상자의 컨트롤에 대하여 대화의 [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 함수가 이 작업을 수행하기에 좋습니다.  
  
-   사용자가 컨트롤과의 상호 작용으로, 다양한 알림 메시지를 보낼 것입니다.   [GetPos](../Topic/CSliderCtrl::GetPos.md) 멤버 함수를 호출하여 컨트롤에서 슬라이더 값을 추출할 수 있습니다.  
  
-   컨트롤을 사용하여 끝나면 제대로 소멸 되었는지 확인해야 합니다.  대화 상자에서 슬라이더 컨트롤을 하는 경우   `CSliderCtrl`  개체는 자동으로 소멸됩니다.  그렇지 않은 경우, 컨트롤 및  `CSliderCtrl`  개체가 제대로 소멸되었는지 확인해야 합니다.  
  
## 참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)