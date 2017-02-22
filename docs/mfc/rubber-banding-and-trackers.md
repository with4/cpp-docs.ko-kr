---
title: "고무 밴드 및 추적기 | Microsoft Docs"
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
  - "CRectTracker 클래스, 추적기 구현"
  - "OLE 개체, 선택"
  - "고무 밴드"
  - "추적기"
  - "WM_LBUTTONDOWN"
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 고무 밴드 및 추적기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

추적기와 함께 공급된 또 다른 기능은 사용자가 선택된 항목 주변의 크기 조정 사각형을 드래그하여 다수의 OLE 항목을 선택하도록 하는 "고무밴드" 선택 영역 기능입니다.  사용자가 마우스 왼쪽 버튼을 놓을 때, 사용자가 선택한 영역 안의 항목이 선택되고 사용자에 의해 조작될 수 있습니다.  예를 들어, 사용자는 선택 영역을 다른 컨테이너 응용 프로그램으로 드래그할 수 있습니다.  
  
 이 기능을 수행하는 것은 사용자 응용 프로그램의 `WM_LBUTTONDOWN` 처리기 함수에서 특정 추가 코드를 요구합니다.  
  
 다음 코드 샘플은 고무밴드 선택 영역 기능과 추가 기능을 수행합니다.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/CPP/rubber-banding-and-trackers_1.cpp)]  
  
 사용자가 고무 밴드 기능을 사용하는 동안 추적기의 가역 방향을 허용하기를 바란다면, 세 번째 매개 변수를 **TRUE**로 설정하여 [CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)을 호출하세요.  가역 방향을 허용하는 것은 때때로 뒤집히기 위해서 [CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)를 유발한다는 것을 기억하세요.  이것은 [CRect::NormalizeRect](../Topic/CRect::NormalizeRect.md)으로 호출하는 방법으로 해결될 수 있습니다.  
  
 자세한 내용은 [Container Client Item](../mfc/containers-client-items.md) 및 [Customizing Drag and Drop](../mfc/drag-and-drop-customizing.md)을 참조하십시오.  
  
## 참고 항목  
 [추적기: OLE 응용 프로그램에서 추적기 구현](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker Class](../mfc/reference/crecttracker-class.md)