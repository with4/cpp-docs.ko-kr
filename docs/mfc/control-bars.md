---
title: "컨트롤 막대 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3550043e5b85247d4188c830873099c6ea9831a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="control-bars"></a>컨트롤 막대
"컨트롤 막대"에 도구 모음, 상태 표시줄 및 대화 상자 모음에 대 한 일반 이름입니다. MFC 클래스 `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, 및 **CReBar** 클래스에서 파생 [CControlBar](../mfc/reference/ccontrolbar-class.md), 공통 기능을 구현 하는입니다.  
  
 컨트롤 막대는 된 사용자 수 옵션을 선택, 명령을 실행 또는 프로그램 정보를 가져올 컨트롤의 행을 표시 하는 창입니다. 도구 모음, 대화 상자 모음 및 상태 표시줄 컨트롤 막대의 종류를 포함 합니다.  
  
-   도구 모음 클래스에서 [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   클래스에서 상태 표시줄, [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   클래스에서 대화 상자 모음 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   클래스에서 rebars [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  MFC 버전 4.0 기준으로 도구 모음, 상태 표시줄 및 도구 설명 구현 됩니다 comctl32.dll MFC에 특정 이전 구현에서에서 구현 되는 시스템 기능을 사용 하 여 합니다. Mfc 버전 6.0 **CReBar**, comctl32.dll 기능을 래핑하는 추가 되었습니다.  
  
 컨트롤 막대의 종류에 대 한 간략 한 소개를 수행 합니다. 자세한 내용은 아래 링크를 참조 하세요.  
  
## <a name="control-bars"></a>컨트롤 막대  
 컨트롤 막대 빠른, 1 단계 명령 동작을 제공 하 여 프로그램의 사용 편의성을 크게 향상 합니다. 클래스 `CControlBar` 모든 도구 모음, 상태 표시줄 및 대화 상자 막대의 공통 기능을 제공 합니다. `CControlBar`부모 프레임 창에서 컨트롤 막대 위치를 지정 하는 기능을 제공 합니다. 컨트롤 막대는 일반적으로 부모 프레임 창의 자식 창, 되므로 클라이언트 보기 또는 프레임 창의 MDI 클라이언트에 "형제" 합니다. 컨트롤 막대 개체 자체를 배치 하는 부모 창의 클라이언트 영역에 대 한 정보를 사용 합니다. 그런 다음 클라이언트 보기 또는 MDI 클라이언트 창을 전체 클라이언트 창의 나머지 되도록 부모의 나머지 클라이언트 창 영역을 변경 합니다.  
  
> [!NOTE]
>  컨트롤 막대의 단추에 없는 경우는 **명령** 또는 **UPDATE_COMMAND_UI** 처리기 프레임 워크에서 단추를 자동으로 비활성화 합니다.  
  
## <a name="toolbars"></a>도구 모음  
 도구 모음은 명령을 수행 하는 비트맵 단추 행을 표시 하는 컨트롤 막대입니다. 해당 메뉴 항목;를 선택 하는 도구 모음 단추를 누르면 메뉴 항목에 매핑된 해당 메뉴 항목에 도구 모음 단추와 동일한 ID를 하는 경우 동일한 처리기를 호출 합니다. 단추는 누름 단추, 라디오 단추 또는 확인란 기호로 표시 및 동작을 구성할 수 있습니다. 도구 모음을 일반적으로 프레임 창의 위쪽에 맞춰집니다 있지만 MFC 도구 모음 "도킹" 해당 부모 창 또는 미니 프레임 창에는 float 모든 면에. 도구 모음 부동할 수도 있으며"" 하 고 크기를 변경할 수 있으며 마우스로 끌 수 있습니다. 사용자는 도구 모음 단추 위로 마우스를 이동할 때 도구 모음에 도구 설명을 표시할 수도 있습니다. 도구 설명은 간단 하 게 단추의 용도 설명 하는 작은 팝업 창.  
  
> [!NOTE]
>  클래스는 MFC 버전 4.0부터 [CToolBar](../mfc/reference/ctoolbar-class.md) Windows 도구 모음 공용 컨트롤을 사용 합니다. A `CToolBar` 포함 한 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)합니다. 이전 도구 모음은 여전히 지원 됩니다. 문서 참조 [도구 모음](../mfc/mfc-toolbar-implementation.md)합니다.  
  
## <a name="status-bars"></a>상태 표시줄  
 상태 표시줄은 텍스트 출력 창 또는 "지표"를 포함 하는 컨트롤 막대 출력 창 및 상태 표시기 메시지 선으로 자주 사용 됩니다. 메시지 줄의 예로 명령줄 도움말 메시지는 선택 된 메뉴 또는 MFC 응용 프로그램 마법사에서 만든 기본 상태 표시줄의 맨 왼쪽 창에서 도구 모음 명령을 간략하게 설명 합니다. 상태 표시기 예제 SCROLL LOCK, NUM LOCK 및 다른 키를 포함 합니다. 상태 표시줄은 일반적으로 프레임 창의 아래쪽에 정렬 됩니다. 클래스 참조 [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 클래스 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)합니다.  
  
## <a name="dialog-bars"></a>대화 상자 모음  
 대화 상자 막대에는 모덜리스 대화 상자의 기능을 갖춘 대화 상자 템플릿 리소스에 따라, 컨트롤 막대가입니다. 대화 상자 모음 창을 포함할 수 있습니다, 사용자 지정 또는 ActiveX 컨트롤입니다. 대화 상자에서와 같이 사용자 컨트롤 간에 탭 수 있습니다. 대화 상자 막대를 위쪽, 아래쪽, 왼쪽 또는 프레임 창의 오른쪽에 맞출 수 있습니다 및 프레임 창에도 이동할 수 있습니다. 클래스 참조 [CDialogBar](../mfc/reference/cdialogbar-class.md)합니다.  
  
## <a name="rebars"></a>Rebars  
 A [rebar](../mfc/using-crebarctrl.md) rebar 컨트롤에 도킹, 레이아웃, 상태 및 지 속성 정보를 제공 하는 컨트롤 막대입니다. Rebar 개체에는 자식 창, 일반적으로 다른 컨트롤을 편집 상자, 도구 모음, 목록 상자 등의 다양 한 포함 될 수 있습니다. Rebar 개체는 지정 된 비트맵을 통해 해당 자식 창을 표시할 수 있습니다. 다시 조정할 수 있습니다 자동 또는 수동으로 클릭 하거나 그리퍼 막대를 끌어 합니다. 클래스 참조 [CReBar](../mfc/reference/crebar-class.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
