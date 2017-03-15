---
title: "현재 뷰 관리 | Microsoft Docs"
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
  - "프레임 창의 현재 뷰"
  - "뷰 비활성화"
  - "프레임 창, 현재 뷰"
  - "OnActivateView 메서드"
  - "뷰, 활성화"
  - "뷰, 및 OnActivateView 메서드"
  - "뷰, 현재"
  - "뷰, 비활성화"
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 현재 뷰 관리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프레임 창의 기본 구현의 일부로 프레임 창은 현재 활성 뷰의 추적을 유지합니다.  분할자 창의 예시와 같이 프레임 창이 하나 이상의 뷰를 포함하는 경우, 현재 뷰는 가장 최근에 사용된 뷰입니다.  활성 뷰는 Windows 나 현재 입력된 포커스를 현재 창과 무관 합니다.  
  
 활성 뷰가 바뀌면, 프레임워크는 해당 [OnActivateView](../Topic/CView::OnActivateView.md) 멤버 함수를 호출하여 현재 뷰를 알립니다.  `OnActivateView`'s `bActivate` 매개 변수를 시험하여 뷰가 활성화 되었는지에 대한 여부를 알릴 수 있습니다.  기본적으로 `OnActivateView`는 정품 인증의 현재 보기에 포커스를 설정 합니다.  `OnActivateView` 를 재정의 하여 뷰가 재활성화 되거나 비활성화 될 때 특별한 처리작업을 수행할 수 있습니다.  예를 들어, 현재 보기에서 다른 비활성 뷰와 구분할 수 있는 특별한 시각적 신호를 제공 하는 것이 좋습니다.  
  
 [Command Routing](../mfc/command-routing.md) 에 설명된 대로 프레임 창은 명령에 해당 \(활성화된\) 뷰를 표준 명령 라우팅의 일부로 제공합니다.  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)