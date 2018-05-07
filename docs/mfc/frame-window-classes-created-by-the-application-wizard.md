---
title: 응용 프로그램 마법사로 만든 프레임 창 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CMainFrame
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3446de072266fdf7661d2e8d8ca0fc968279646
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>응용 프로그램 마법사로 만든 프레임 창 클래스
사용 하는 경우는 [응용 프로그램 마법사](../ide/creating-desktop-projects-by-using-application-wizards.md) 응용 프로그램, 문서 및 뷰 클래스 외에도 기본 응용 프로그램을 만드는 응용 프로그램 마법사는 응용 프로그램의 주 프레임 창에 대 한 파생된 프레임 창 클래스를 만듭니다. 라고 `CMainFrame` 를 포함 하는 파일이 고, 기본적으로 해당 라고 합니다. H와 해당 합니다. CPP 합니다.  
  
 SDI 응용 프로그램이 경우 프로그램 `CMainFrame` 클래스에서 파생 되므로 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다.  
  
 응용 프로그램이 MDI 경우 `CMainFrame` 클래스에서 파생 된 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)합니다. 이 경우 `CMainFrame` 메뉴, 도구 모음 및 상태 표시줄을 보유 하는 주 프레임을 구현 합니다. 응용 프로그램 마법사는 새 문서 프레임 창 클래스를 파생 되지 않습니다. 기본 구현을 사용 하 여 대신 [CMDIChildWnd 클래스](../mfc/reference/cmdichildwnd-class.md)합니다. MFC 프레임 워크에는 각 보기를 포함 하는 자식 창을 만듭니다 (형식 중 하나일 수 있는 `CScrollView`, `CEditView`, `CTreeView`, `CListView`등)는 응용 프로그램에 필요한 합니다. 문서 프레임 창을 사용자 지정 해야 하는 경우 새 문서 프레임 창 클래스를 만들 수 있습니다 (참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md)).  
  
 클래스에 형식의 멤버 변수가 도구 모음을 지원 하도록 선택 하면 [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 `OnCreate` 두 초기화 하는 메시지-처리기 함수의 [ 컨트롤 막대](../mfc/control-bars.md)합니다.  
  
 이러한 프레임 창 클래스 만들어진 대로 작동 하지만 해당 기능을 향상 시키려면 멤버 변수 및 멤버 함수를 추가 해야 합니다. 창 클래스 다른 Windows 메시지를 처리할 수도 있습니다. 자세한 내용은 참조 [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 클래스](../mfc/frame-window-classes.md)   
 [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/mfc-program-or-control-source-and-header-files.md)

