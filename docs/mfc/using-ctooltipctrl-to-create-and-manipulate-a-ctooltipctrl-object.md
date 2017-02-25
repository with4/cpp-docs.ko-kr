---
title: "CToolTipCtrl을 사용하여 CToolTipCtrl 개체 만들기 및 조작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl 클래스, using"
  - "도구 설명[C++], 만들기"
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CToolTipCtrl을 사용하여 CToolTipCtrl 개체 만들기 및 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) 사용에 대한 예제입니다.  
  
### CToolTipCtrl 를 만들고 조작하려면  
  
1.  `CToolTipCtrl` 개체를 생성합니다.  
  
2.  [Create](../Topic/CToolTipCtrl::Create.md) 을 호출하여 Windows 공용 컨트롤 도구 팁을 만들고 `CToolTipCtrl` 개체에 연결하십시오.  
  
3.  [AddTool](../Topic/CToolTipCtrl::AddTool.md) 를 호출하여 도구는 도구 팁 컨트롤을 사용하여 등록하십시오. 이렇게 하면 도구 팁에 저장된 정보는 커서가 도구에 올라오면 나타납니다.  
  
4.  [SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md) 를 호출하여 도구에 대해 도구 팁이 가지고 있는 정보를 설정합니다.  
  
5.  [SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md) 를 호출하여 도구의 새 경계 사각형을 설정합니다.  
  
6.  [HitTest](../Topic/CToolTipCtrl::HitTest.md) 를 호출하여 주어진 도구의 경계 사각형 안에 있는지 여부를 결정하기 위해 포인터를 확인하고 그렇다면 도구와 관련된 정보를 수집합니다.  
  
7.  [GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md) 를 호출하여 도구 팁 컨트롤을 사용하여 등록된 도구의 개수를 검색합니다.  
  
## 참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)