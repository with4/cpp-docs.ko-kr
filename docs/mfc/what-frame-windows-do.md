---
title: "프레임 창의 역할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5143bab1ea84392efe1bd5783889c45375365ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="what-frame-windows-do"></a>프레임 창의 기능
단순한 뷰 프레임 지정 외에도 프레임 창은 프레임을 해당 뷰 및 응용 프로그램에서 조정하는 것과 관련된 여러 작업을 수행합니다. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 및 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 에서 상속 [CFrameWnd](../mfc/reference/cframewnd-class.md)갖추고 있으므로, `CFrameWnd` 으로 기능을 더 추가 하는 새로운 기능입니다. 자식 창 예에는 뷰, 단추 및 목록 상자와 같은 컨트롤, 도구 모음, 상태 표시줄 및 대화 상자 막대를 비롯한 컨트롤 막대가 포함됩니다.  
  
 프레임 창은 해당 자식 창의 레이아웃을 관리합니다. MFC 프레임워크에서 프레임 창은 클라이언트 영역 내에 모든 컨트롤 막대, 뷰 및 기타 자식 창을 배치합니다.  
  
 프레임 창은 또한 명령을 해당 뷰로 전달하며, 컨트롤 창으로부터 알림 메시지에 응답할 수 있습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [컨트롤 막대 (어떻게 배치 되는 프레임 창에)](../mfc/control-bars.md)  
  
-   [메뉴, 컨트롤 막대 및 액셀러레이터 (어떻게 배치 되는 프레임 창에) 관리](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [명령 라우팅 (프레임 창에서 해당 뷰 및 기타 명령 대상으로)](../mfc/command-routing.md)  
  
-   [문서 /View 아키텍처](../mfc/document-view-architecture.md)  
  
-   [컨트롤 막대](../mfc/control-bars.md)  
  
-   [컨트롤](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창](../mfc/frame-windows.md)

