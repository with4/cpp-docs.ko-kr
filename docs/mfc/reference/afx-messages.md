---
title: "AFX 메시지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
dev_langs:
- C++
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41f300f285fb4eaf1a6154a21cbbabc0253fc730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="afx-messages"></a>AFX 메시지
이러한 메시지는 MFC에서 사용 됩니다.  
  
## <a name="messages"></a>메시지  
 다음 표에서 MFC 라이브러리에 사용 되는 메시지를 나열 합니다.  
  
||||||  
|-|-|-|-|-|  
|메시지|설명|[in] `wParam`|`lParam`(모든 매개 변수는 [in] 언급이 없으면.)|반환 값|  
|AFX_WM_ACCGETOBJECT|사용되지 않습니다.|사용되지 않습니다.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_ACCGETSTATE|내게 필요한 옵션 지원에 사용 됩니다. 이 메시지를 보내 `CMFCPopupMenu` 또는 `CMFCRibbonPanelMenu` 를 현재 요소의 상태를 검색 합니다.|메뉴 단추 또는 구분 될 수 있는 요소의 인덱스입니다.|사용되지 않습니다.|요소 상태입니다. 인덱스가 유효 하지 않을 경우에-1을은 메뉴 단추에 특수 특성이 없는 경우 0입니다. 그렇지 않으면 다음 플래그의 조합입니다.<br /><br /> TBBS_DISABLED-항목은 사용할 수 없습니다.<br /><br /> 항목이 선택 되었으면 TBBS_CHECKED-<br /><br /> TBBS_BUTTON-해당 항목은 표준 누름<br /><br /> 단추를 누르면 TBBS_PRESSED-<br /><br /> TBBS_INDETERMINATE-정의 되지 않은 상태<br /><br /> TBBS_SEPARATOR-메뉴 단추가 아닌, 다른 메뉴 항목 간의 분리는이 요소 양식|  
|AFX_WM_CHANGE_ACTIVE_TAB|프레임 워크는 크기 조정 가능한 컨트롤 막대 컨트롤에이 메시지를 보냅니다. 알림을 수신 하려면이 메시지를 처리 `CMFCTabCtrl` 사용자 활성 탭이 변경 될 때 개체입니다.|탭의 인덱스입니다.|사용되지 않습니다.|0이 아닙니다.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|프레임 워크의 부모에이 메시지를 보냅니다 `CMFCShellListCtrl` 사용자가 현재 폴더를 변경 하는 경우.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_CHANGEVISUALMANAGER|프레임 워크는 현재 비주얼 관리자를 변경할 때 모든 프레임 창에이 메시지를 보냅니다. 이 메시지에 대 한 응답으로 프레임 창을 해당 영역을 다시 계산 하 고 필요에 따라 다른 매개 변수를 조정 합니다. 이 이벤트에 대 한 알림이 표시 하는 경우 응용 프로그램에서 AFX_WM_CHANGEVISUALMANAGER 메시지를 처리할 수 있습니다. 기본 클래스 처리기를 호출 해야 합니다 (`OnChangeVisualManager`) 프레임 워크의 내부 되도록이 이벤트 처리는 수행 됩니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_CHANGING_ACTIVE_TAB|부모에 보냅니다 `CMFCTabCtrl` 개체입니다.  알림을 수신 하려는 경우이 메시지를 처리 `CMFCTabCtrl` 탭을 재설정 하는 개체입니다.|활성화 되는 탭의 인덱스입니다.|사용되지 않습니다.|0이 아닙니다.|  
|AFX_WM_CHECKEMPTYMINIFRAME|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_CREATETOOLBAR|보낸 `CMFCToolBarsListPropertyPage` 만드는 사용자는 새 도구 모음 사용자 지정 프로세스 중입니다. 사용자 지정 CMFCToolBar 파생 된 개체를 인스턴스화할이 메시지를 처리할 수 있습니다. 이 메시지를 처리 하 고 사용자 지정 도구 모음을 만들 경우 기본 처리기로 호출을 생략 합니다.|사용되지 않습니다.|도구 모음의 이름을 포함 하는 문자열에 대 한 포인터입니다.|새로 만든된 도구 모음에 대 한 포인터입니다. NULL은 도구 모음 만들기가 취소 되었음을 나타냅니다.|  
|AFX_WM_CUSTOMIZEHELP|사용자 지정 속성 시트에서 주 프레임 창에 보내는 `CMFCToolbarCustomize Dialog` 를 누를 때는 **도움말** 단추를 클릭 하거나 F1 키입니다.|사용자 지정 속성 시트의 활성 페이지를 지정합니다.|에 대 한 포인터는 `CMFCToolbarCustomize Dialog` 개체입니다.|0입니다.|  
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog` 사용자가 새 도구 모음을 만드는 부모 프레임에 알리기 위해이 메시지를 보냅니다.|`TRUE`사용자 지정 시작 되 면 `FALSE` 사용자 지정이 완료 되 면입니다.|사용되지 않습니다.|0입니다.|  
|AFX_WM_DELETETOOLBAR|사용자를 사용자 지정 모드에 대 한 도구 모음을 삭제 하려고 할 때 주 프레임 창으로 보냅니다.<br /><br /> 사용자는 사용자 지정 모드의 도구 모음을 삭제할 때 추가 작업을 수행 하려면이 메시지를 처리 합니다. 또한 기본 처리기를 호출 해야 (`OnToolbarDelete`), 도구 모음을 삭제 하 합니다. 기본 처리기는 도구 모음을 삭제할 수 있는지 여부를 나타내는 값을 반환 합니다.|사용되지 않습니다.|에 대 한 포인터는 `CMFCToolBar` 삭제할 개체입니다.|도구 모음을 삭제할 수 없습니다. 0이 아닌 그렇지 않으면 0입니다.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`문서 색을 검색 하는 주 프레임 창에이 메시지를 보냅니다.|사용되지 않습니다.|[out에서] 에 대 한 포인터는 `CList<COLORREF, COLORREF>` 개체입니다.|0입니다.|  
|AFX_WM_GETDRAGBOUNDS|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|사용자는 리본 목록 항목을 강조 표시할 때 주 프레임 창으로 보냅니다.|강조 표시 된 항목의 인덱스|에 대 한 포인터`CMFCBaseRibbonElement`|사용되지 않습니다.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|부모에 보냅니다 `CMFCShellListCtrl` 또는 `CMFCShellTreeCtrl` 사용자 완료할 셸 명령을 실행 하는 경우를 제어 합니다.|사용자가 실행 된 명령 ID|사용되지 않습니다.|응용 프로그램에서이 메시지를 처리 하는 경우 0을 반환 합니다.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|프레임 워크 팝업 메뉴를 표시 하기 전에 리본 메뉴의 부모에이 메시지를 보냅니다. 이 메시지를 처리 하 고 팝업 메뉴 언제 든 지 수정할 수 있습니다.|사용되지 않습니다.|에 대 한 포인터`CMFCBaseRibbonElement`|사용되지 않습니다.|  
|AFX_WM_ON_CANCELTABMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|프레임 워크 활성 리본 컨트롤 범주를 변경할 때 주 프레임에이 메시지를 보냅니다.|사용되지 않습니다.|에 대 한 포인터는 `CMFCRibbonBar` 해당 범주가 변경 되었습니다.|사용되지 않습니다.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|프레임 워크의 소유자에 게 알리도록이 메시지를 보냅니다 `CMFCDesktopAlertWnd` 기간은를 닫아야 합니다.|사용되지 않습니다.|에 대 한 포인터 `CMFCDesktopAlertWnd` 개체입니다.|사용되지 않습니다.|  
|AFX_WM_ON_DRAGCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|사용자 지정 도구 설명을 사용 하는 경우 탭 창을는 탭에 대 한 도구 설명이 표시 하려고 할 때 주 프레임 창으로 보냅니다.|사용되지 않습니다.|에 대 한 포인터는 `CMFCTabToolTipInfo` 구조입니다.|사용되지 않습니다.|  
|AFX_WM_ON_HSCROLL|크기 조정 가능한 컨트롤 막대 컨트롤에 전달 합니다. 알림을 수신 하려면이 메시지를 처리 `CMFCTabCtrl` 탭된 위젯 가로 스크롤 막대의 스크롤 이벤트가 발생할 때 개체입니다.|사용자 지정 하는 스크롤 막대 값 요청 스크롤의 하위 단어를 지정 합니다.  자세한 내용은 이 항목 뒷부분에 나오는 표를 참조하십시오.|사용되지 않습니다.|0이 아닙니다.|  
|AFX_WM_ON_MOVE_TAB|사용자가을 새 위치로 탭을 끌 때 탭된 창의 부모에 보냅니다.|원래 위치에 있는 탭의 0부터 시작 하는 인덱스입니다.|[out] 새 위치에 있는 탭의 0부터 시작 하는 인덱스입니다.|0입니다.|  
|AFX_WM_ON_MOVETABCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_ON_MOVETOTABGROUP|사용자 MDI 자식 창에 한 탭된 그룹에서 다른 위치로 이동 하는 경우에 주 프레임 창으로 보냅니다.|탭된 창에 대 한 핸들 (`CMFCTabCtrl`)에서 MDI 자식 창을 제거 되었습니다.|[out] 탭된 창에 대 한 핸들 (`CMFCTabCtrl`) MDI 자식 창을 삽입 되었습니다.|무시됩니다.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|부모에 보냅니다 `CDockablePane` 을 클릭할 때는 **닫기** 컨트롤 막대의 캡션 단추입니다.|사용되지 않습니다.|사용자 클릭 하면 도킹 가능한 창에 대 한 포인터는 **닫기** 단추입니다.|`TRUE`경우 창을 닫을 수 없습니다. 그렇지 않으면 FALSE입니다.|  
|AFX_WM_ON_RENAME_TAB|편집 가능한 탭 이름을 바꾼 후에 탭된 창의 부모에 보냅니다.|이름이 바뀐된 탭의 0부터 시작 하는 인덱스입니다.|[out] 새 탭 이름을 포함 하는 문자열에 대 한 포인터입니다.|응용 프로그램;이 메시지를 처리 하는 경우 0이 아닌 프레임 워크에서 호출을 표시 하지 않을 `CMFCBaseTabCtrl::SetTabLabel`합니다.  그런 다음 0이 반환 되 면 `CMFCBaseTabCtrl::SetTabLabel` 프레임 워크에서 호출 됩니다.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|사용자가 사용자 지정을 시작할 때 부모 프레임으로 보냅니다. 사용자 고유의 사용자 지정 대화 상자를 표시 하려는 경우이 메시지를 처리 합니다.|사용되지 않습니다.|사용자 지정할 수 리본 컨트롤에 대 한 포인터입니다.|응용 프로그램이이 메시지를 처리 하 고 자체 사용자 지정 대화 상자를 표시 하는 경우에 0이 아닙니다. 0을 반환 하는 응용 프로그램 프레임 워크에는 기본 제공 사용자 지정 대화 상자가 표시 됩니다.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX_WM_POSTSETPREVIEWFRAME|주 프레임에 사용자의 인쇄 미리 보기 모드 변경 되었음을 알리기 위해 전송|`TRUE`인쇄 미리 보기 모드가 설정 되어 있는지를 나타냅니다. `FALSE`해당 인쇄 미리 보기 모드를 해제를 나타냅니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_PROPERTY_CHANGED|속성 표 컨트롤의 소유자에 게 보낸 (`CMFCPropertyGridCtrl`) 사용자는 선택한 속성의 값을 변경 하는 경우.|속성 목록의 컨트롤 ID입니다.|속성에 대 한 포인터 (`CMFCPropertyGridProperty`) 변경 합니다.|사용되지 않습니다.|  
|AFX_WM_RESETCONTEXTMENU|사용자는 상황에 맞는 메뉴 사용자 지정 하는 동안 새로 고칠 때 주 프레임 창으로 보냅니다.|상황에 맞는 메뉴의 리소스 ID입니다.|현재 상황에 맞는 메뉴에 대 한 포인터 `CMFCPopupMenu`합니다.|사용되지 않습니다.|  
|AFX_WM_RESETKEYBOARD|프레임 워크는 사용자 지정 하는 동안 모든 키보드 액셀러레이터를 재설정 하는 사용자는 주 프레임 창에이 메시지를 보냅니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_RESETMENU|프레임 워크 메뉴 소유자 (프레임 창)에이 메시지를 보내는 사용자 응용 프로그램 프레임 메뉴 사용자 지정 동안 다시 설정|메뉴 리소스 id입니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_RESETPROMPT|프레임 워크는 사용자 지정 대화 상자 도구 모음에서 도구 모음을 사용자 재설정 하는 경우이 메시지를 보냅니다. 기본 처리기에는 사용자가 도구 모음 다시 설정 하려는 여부를 묻는 메시지 상자가 표시 됩니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_RESETTOOLBAR|A `CMFCToolBar` 도구 모음이 복원 되 면 원래 상태로 즉, 리소스에서 로드 된 개체에서이 메시지를 보냅니다. 해당 클래스에서 파생 되는 도구 모음 단추 재진입이 메시지를 처리 `CMFCToolbarButton`합니다. 자세한 내용은 `CMFCToolbarComboBoxButton`을 참조하세요.|상태가 복원 된 도구 모음 리소스 ID입니다.|사용되지 않습니다.|0입니다.|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`개체는 일반 메뉴 단추를 클릭할 때 해당 소유자에 게이 메시지를 보냅니다. 사용 될 때마다가이 메시지를 처리 `CMFCToolbarMenuButton` 단추를 클릭할 때 팝업 메뉴를 표시 합니다.|메시지를 보내는 단추의 명령 ID입니다.|커서의 화면 좌표입니다. 하위 단어에 대 한 x-좌표를 지정합니다. 상위 단어에 대 한 y-좌표를 지정합니다.|사용되지 않습니다.|  
|AFX_WM_TOOLBARMENU|마우스 포인터가 클라이언트 또는 창의 비클라이언트 영역에 있는 동안 마우스 오른쪽 단추를 놓을 때 주 프레임 창으로 보냅니다.|사용되지 않습니다.|마우스 포인터의 화면 좌표입니다. 하위 단어에 대 한 x-좌표를 지정합니다. 상위 단어에 대 한 y-좌표를 지정합니다.|응용 프로그램;이 메시지를 처리 하는 경우 0 그렇지 않으면 0이 아닌 값입니다.|  
|AFX_WM_UPDATETOOLTIPS|전송 모든 도구 설명 소유자에 게 해당 도구 설명 컨트롤 다시 만들어야 합니다.|이 메시지를 처리 해야 하는 컨트롤의 형식입니다. 가능한 값 목록은이 항목의 뒷부분에 나오는 표를 참조 하세요.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`사용자가 부모 프레임에이 메시지를 보냅니다는 **도움말** 단추를 클릭 하 여 도움말 모드를 시작 또는 **도움말** 캡션 단추를 클릭 하거나 F1 키입니다.|사용되지 않습니다.|인스턴스에 대 한 포인터 `CMFCWindowsManagerDialog`합니다.|사용되지 않습니다.|  
  
 다음 표에서의 낮은 단어에 대 한 값을 보여 줍니다.는 `lParam` AFX_WM_HSCROLL 메서드의 매개 변수:  
  
|||  
|-|-|  
|값|의미|  
|SB_ENDSCROLL|사용자는 스크롤을 종료합니다.|  
|SB_LEFT|사용자는 왼쪽으로 스크롤됩니다.|  
|SB_RIGHT|사용자는 오른쪽 아래로 스크롤합니다.|  
|SB_LINELEFT|사용자는 단위로 한 단위씩 왼쪽으로 스크롤합니다.|  
|SB_LINERIGHT|사용자는 단위로 한 단위씩 오른쪽을 스크롤합니다.|  
|SB_PAGELEFT|사용자는 창의 너비 만큼 왼쪽으로 스크롤합니다.|  
|SB_PAGERIGHT|사용자 오른쪽 창의 너비 스크롤합니다.|  
|SB_THUMBPOSITION|사용자가 끌어 스크롤 상자 (thumb) 하 고 마우스 단추를 해제 합니다. 상위 단어 끌기 작업의 끝에 있는 스크롤 상자 위치를 나타냅니다.|  
|SB_THUMBTRACK|사용자가 스크롤 상자를 끌고 있습니다. AFX_WM_ON_HSCROLL 메시지 마우스 단추를 놓을 때까지 반복 해 서이 값으로 전송 됩니다. 상위 단어로 스크롤 상자 끌어 놓은 위치를 나타냅니다.|  
  
> [!NOTE]
>  상위 단어는 `lParam` 그렇지 않으면이 단어를 사용 하지는; 매개 변수는 하위 단어 SB_THUMBPOSITION 있느냐 SB_THUMBTRACK 스크롤 상자의 현재 위치를 지정 합니다.  
  
 에 대 한 플래그 값을 나열 하는 다음 표에 `lParam` AFX_WM_UPDATETOOLTIPS 메시지의 매개 변수:  
  
|||  
|-|-|  
|플래그|값|  
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|  
|AFX_TOOLTIP_TYPE_TAB|0x0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
