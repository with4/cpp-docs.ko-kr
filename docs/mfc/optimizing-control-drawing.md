---
title: "컨트롤 그리기 최적화 | Microsoft Docs"
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
  - "MFC ActiveX 컨트롤, 최적화"
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 컨트롤 그리기 최적화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤 컨테이너 공급 장치 컨텍스트에 자신을 그리도록 지시 할 때, 그것은 일반적으로 디바이스 컨텍스트로 \(예 : 펜, 브러쉬, 및 폰트 등\) GDI 객체를 선택의 드로잉 동작을 수행하고, 이전의 GDI 객체를 복원합니다.  컨테이너는 동일한 디바이스 컨텍스트에 그려지는 여러 컨트롤이 있고 각 컨트롤이 선택된 경우 GDI는 컨트롤이 개별적으로 이전에 선택한 개체를 복원하지 않으면 시간을 절약 할 수 필요로하는 개체입니다.  모든 컨트롤이 그려진 후 컨테이너는 자동으로 원래의 객체를 복원 할 수 있습니다.  
  
 컨테이너는이 방법을 지원 하는지 여부를 검색하기 위해 컨트롤은  [COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md) 멤버 함수를 호출할 수 있습니다.  이 함수가  **TRUE**을  반환 하는 경우, 컨트롤이 이전에 선택된 개체를 복원하는 일반적인 단계를 건너뛸 수 있습니다.  
  
 다음  `OnDraw`  함수\(최적화 되지 않음\)를 갖는 컨트롤을 고려합니다:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/CPP/optimizing-control-drawing_1.cpp)]  
  
 예제에서 펜과 브러시는 지역 변수입니다, 범위를 벗어날 때 \( `OnDraw` 함수가 끝날 때\) 그 소멸자 호출 된다는 의미입니다.  소멸자는 해당 GDI 개체를 삭제하려고 합니다.  `OnDraw`로부터 반환 후, 디바이스 컨텍스트에 선택된 상태로하려면 삭제하면 안됩니다.  
  
 `OnDraw` 가 완료될 때[CPen](../mfc/reference/cpen-class.md) 및  [CBrush](../mfc/reference/cbrush-class.md)개체가 소멸되는것을 방지하기 위해서는,지역 변수가 아닌 멤버 변수에 저장합니다.  컨트롤의 클래스 선언에 두 개의 새 멤버 변수 선언을 추가합니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/CPP/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/CPP/optimizing-control-drawing_3.h)]  
  
 다음과 같이`OnDraw` 함수를 다시 쓸 수 있습니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/CPP/optimizing-control-drawing_4.cpp)]  
  
 이 방법을 사용하면   `OnDraw` 를 호출할 때마다 펜 및 브러시 생성을 피할 수 있습니다.  속도가 빨라지는 추가 인스턴스 데이터를 유지합니다.  
  
 ForeColor 또는 BackColor 속성이 변경되면 펜 또는 브러시를 다시 만들어야 합니다.  이 작업을 위해 [OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md) 및  [OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md) 멤버 함수를 재정의합니다:  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/CPP/optimizing-control-drawing_5.cpp)]  
  
 마지막으로, 불필요한  `SelectObject`  호출을 제거하기 위해, `OnDraw` 을 다음과 같이 수정합니다:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/CPP/optimizing-control-drawing_6.cpp)]  
  
## 참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)   
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX 컨트롤: ActiveX 컨트롤 그리기](../mfc/mfc-activex-controls-painting-an-activex-control.md)