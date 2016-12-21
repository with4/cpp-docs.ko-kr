---
title: "프레임 창의 기능 | Microsoft Docs"
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
  - "프레임 창, 프레임 창 정보"
  - "프레임 창, 작업"
  - "MFC, 프레임 창"
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임 창의 기능
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

간단한 뷰 프레이밍 외에도, 프레임 창은 그들의 뷰와 응용 프로그램을 사용한 프레임 조정과 관련된 다양한 작업에 책임이 있습니다.  [CFrameWnd](../mfc/reference/cframewnd-class.md)으로부터 상속된 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 및 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)입니다. 따라서 그들은 그들이 더한 새로운 기능뿐만 아니라  `CFrameWnd` 기능을 가집니다.  자식 창 사례는 도구 모음, 상대 표시줄, 대화 상자 막대를 포함하여 뷰, 단추 및 목록 상자와 컨트롤 막대같은 컨트롤을 포함합니다.  
  
 프레임 창은 자식 창의 레이아웃 관리에 책임이 있습니다.  MFC framework에서, 프레임 창은 모든 컨트롤 막대, 뷰, 다른 자식 창을 그들의 클라이언트 영역 내에 배치합니다.  
  
 프레임 창은 또한 명령을 뷰에 전달하고, 컨트롤 창의 알림 메시지에 응답할 수 있습니다.  
  
## 추가 정보  
  
-   [컨트롤 막대\(프레임 창에 적합해지는 방법\)](../mfc/control-bars.md)  
  
-   [메뉴, 컨트롤 막대 및 액셀러레이터 관리\(프레임 창에 적합해지는 방법\)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [명령 라우팅\(프레임 윈도우에서 그것의 뷰 및 다른 명령 타겟까지\)](../mfc/command-routing.md)  
  
-   [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)  
  
-   [컨트롤 막대](../mfc/control-bars.md)  
  
-   [컨트롤](../mfc/controls-mfc.md)  
  
## 참고 항목  
 [프레임 창](../mfc/frame-windows.md)