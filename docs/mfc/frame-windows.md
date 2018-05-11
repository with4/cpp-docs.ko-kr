---
title: 프레임 창 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515df19bcc11f7a6706985014fc44bc4ff315f36
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="frame-windows"></a>프레임 창
Windows에서 실행 되는 응용 프로그램 프레임 창에 표시 되는 문서와 사용자 상호 작용 합니다. 문서 프레임 창에 두 가지 주요 구성 요소: 프레임과 들어가는 내용이 있습니다. 문서 프레임 창 수는 [단일 문서 인터페이스](../mfc/sdi-and-mdi.md) (SDI) 프레임 창 또는 [다중 문서 인터페이스](../mfc/sdi-and-mdi.md) 자식 창을 (mdi 다중). Windows에서 대부분의 프레임 창에 사용자의 상호 작용: 이동 및 창 크기 조정, 닫기 및 최소화 및 최대화 합니다. 프레임 내의 내용을 관리할 수 있습니다.  
  
## <a name="frame-windows-and-views"></a>프레임 창 및 뷰  
 MFC 프레임 워크는 프레임 창을 사용 하 여 뷰를 포함 합니다. 두 구성 요소-내용이-표시 하 고 MFC의 서로 다른 두 클래스에 의해 관리 됩니다. 프레임 창 클래스에는 프레임을 관리 하 고 뷰 클래스 콘텐츠를 관리 합니다. 보기 창에 프레임 창의 자식입니다. 그리기 및 다른 사용자는 문서와 상호 작용 하지 프레임 창의 클라이언트 영역 보기의 클라이언트 영역에서 수행 합니다. 프레임 창 뷰 캡션 표시줄 및 컨트롤 메뉴를 최소화 하 고 창을 최대화 단추와 같은 표준 창 컨트롤 주위에 프레임을 나타내며 및 창 크기 조정에 대 한 제어 합니다. "콘텐츠" 자식 창에서 완벽 하 게 사용 되 고 창의 클라이언트 영역으로 구성 — 보기. 다음 그림 프레임 창 및 뷰 간의 관계를 보여 줍니다.  
  
 ![프레임 창 보기](../mfc/media/vc37fx1.gif "vc37fx1")  
프레임 창 및 뷰  
  
## <a name="frame-windows-and-splitter-windows"></a>프레임 창 및 분할 창  
 프레임 창의 경우 여러 뷰를 사용 하 여 일반적으로 규정 하는 또 다른 일반적인 해결 방법은 [분할자 창](../mfc/multiple-document-types-views-and-frame-windows.md)합니다. 분할자 창에서 프레임 창의 클라이언트 영역 분할자 창에는 보기 창 이라고 하는 여러 자식 기간을 차지 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
 **일반 프레임 창 항목**  
  
-   [창 개체 소멸 시키기](../mfc/window-objects.md)  
  
-   [프레임 창 클래스](../mfc/frame-window-classes.md)  
  
-   [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
-   [프레임 창 수행할 작업](../mfc/what-frame-windows-do.md)  
  
 **프레임 창 사용에 대 한 항목**  
  
-   [프레임 창 사용](../mfc/using-frame-windows.md)  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [프레임 창 소멸 시키기](../mfc/destroying-frame-windows.md)  
  
-   [MDI 자식 창 관리](../mfc/managing-mdi-child-windows.md)  
  
-   [현재 뷰 관리](../mfc/managing-the-current-view.md) 둘 이상의 뷰가 포함 된 프레임 창에  
  
-   [메뉴, 컨트롤 막대 및 액셀러레이터 (프레임 창 공간을 공유 하는 다른 개체)를 관리 합니다.](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **프레임 창의 특수 기능에 대 한 항목**  
  
-   [파일 끌어서 놓기](../mfc/dragging-and-dropping-files-in-a-frame-window.md) 파일 탐색기 또는 파일 관리자 프레임 창에  
  
-   [동적 데이터 교환 (DDE)에 응답](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [세미 모달 상태: 상황에 맞는 Windows 도움말 (기타 창 작업 조정)](../mfc/orchestrating-other-window-actions.md)  
  
-   [세미 모달 상태: 인쇄 및 인쇄 미리 보기 (기타 창 작업 조정)](../mfc/orchestrating-other-window-actions.md)  
  
 **다른 종류의 창에 대 한 항목**  
  
-   [뷰 사용](../mfc/using-views.md)  
  
-   [대화 상자](../mfc/dialog-boxes.md)  
  
-   [컨트롤](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>참고 항목  
 [Windows](../mfc/windows.md)

