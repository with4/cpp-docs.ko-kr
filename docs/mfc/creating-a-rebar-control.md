---
title: "Rebar 컨트롤 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl 클래스, 만들기"
  - "rebar 컨트롤, 만들기"
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rebar 컨트롤 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CReBarCtrl](../mfc/reference/crebarctrl-class.md) 개체는 부모 개체가 표시 되기 전에 만들어 져야 합니다.  이렇게 하면 칠하기 문제가 발생할 가능성이 최소화 됩니다.  
  
 예를 들어, rebar 컨트롤 \(프레임 창 개체에 사용 되는\)는 일반적으로 도구 모음 컨트롤에 대한 부모 창으로 사용 됩니다.  따라서 rebar 컨트롤의 부모는 프레임 창 개체입니다.  프레임 창 개체는 부모이기 때문에, `OnCreate` 멤버 함수는 rebar 컨트롤을 생성하기 위한 최적의 장소입니다.  
  
 `CReBarCtrl` 개체를 사용하려면, 일반적으로 다음 단계를 수행해야 합니다.  
  
### CReBarCtrl 개체를 사용 하려면  
  
1.  [CReBarCtrl](../mfc/reference/crebarctrl-class.md) 개체를 생성합니다.  
  
2.  [Create](../Topic/CReBarCtrl::Create.md) 을 호출하여 Windows rebar 명령 컨트롤을 만들고 요구되는 스타일을 지정하는 `CReBarCtrl` 개체와 연결하십시오.  
  
3.  rebar 컨트롤 개체의 배경으로 사용되는 [CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md) 를 호출하여 비트맵을 로드하십시오.  
  
4.  자식 창 개체\(도구 모음, 대화 상자 컨트롤 등등\) 를 만들고 초기화하십시오. rebar 컨트롤 개체가 포함합니다.  
  
5.  밴드를 삽입하는데 필요한 정보를 사용하여 **REBARBANDINFO** 구조체를 초기화 하십시오.  
  
6.  [InsertBand](../Topic/CReBarCtrl::InsertBand.md) 를 호출하여 기존 자식 창\(`m_wndReToolBar`와 같은\)을 새 rebar 컨트롤에 삽입하십시오.  기존 rebar 컨트롤에 밴드를 삽입하는 방법에 대한 자세한 내용은 [Rebar Controls and Bands](../mfc/rebar-controls-and-bands.md) 를 참조하십시오.  
  
## 참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)