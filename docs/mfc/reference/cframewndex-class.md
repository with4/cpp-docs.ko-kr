---
title: "CFrameWndEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWndEx class"
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 Windows의 기능 겹쳐진 문서 인터페이스 \(SDI\) 또는 팝업 프레임 창, 단일 및 창 관리에 대 한 멤버를 제공 합니다.  확장 된  [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스입니다.  
  
## 구문  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFrameWndEx::ActiveItemRecalcLayout](../Topic/CFrameWndEx::ActiveItemRecalcLayout.md)|프레임의 클라이언트 영역 및 OLE 클라이언트 항목의 레이아웃을 조정합니다.|  
|`CFrameWndEx::AddDockSite`|이 메서드가 사용되지 않습니다.|  
|[CFrameWndEx::AddPane](../Topic/CFrameWndEx::AddPane.md)|컨트롤 막대 도킹 관리자에 등록합니다.|  
|[CFrameWndEx::AdjustDockingLayout](../Topic/CFrameWndEx::AdjustDockingLayout.md)|레이아웃의 프레임 창에 도킹 된 모든 창 다시 계산 됩니다.|  
|[CFrameWndEx::DelayUpdateFrameMenu](../Topic/CFrameWndEx::DelayUpdateFrameMenu.md)|프레임 메뉴 설정 하 고 명령 처리 유휴 상태일 때 업데이트 됩니다.|  
|[CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md)|지정 된 창 프레임 창에 도킹합니다.|  
|[CFrameWndEx::DockPaneLeftOf](../Topic/CFrameWndEx::DockPaneLeftOf.md)|한 창을 다른 창 왼쪽에 도킹합니다.|  
|[CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md)|지정 된 면의 주 프레임 창에 컨트롤이 도킹 된 경우 창에 대 한 자동 숨기기 모드를 수 있습니다.|  
|[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)|도킹 창 프레임 창에 속해 있습니다.|  
|[CFrameWndEx::EnableFullScreenMainMenu](../Topic/CFrameWndEx::EnableFullScreenMainMenu.md)|표시 하거나 전체 화면 모드에서 기본 메뉴를 숨깁니다.|  
|[CFrameWndEx::EnableFullScreenMode](../Topic/CFrameWndEx::EnableFullScreenMode.md)|프레임 창의 전체 화면 모드를 활성화 합니다.|  
|[CFrameWndEx::EnableLoadDockState](../Topic/CFrameWndEx::EnableLoadDockState.md)|로드의 도킹 상태를 사용할 수 있거나.|  
|[CFrameWndEx::EnablePaneMenu](../Topic/CFrameWndEx::EnablePaneMenu.md)|창 메뉴의 자동 처리를 사용할 수 있거나.|  
|[CFrameWndEx::GetActivePopup](../Topic/CFrameWndEx::GetActivePopup.md)|현재 표시 된 팝업 메뉴에 포인터를 반환 합니다.|  
|[CFrameWndEx::GetDefaultResId](../Topic/CFrameWndEx::GetDefaultResId.md)|프레임 워크는 프레임 창을 로드할 때 사용자가 지정한 리소스 ID를 반환 합니다.|  
|[CFrameWndEx::GetDockingManager](../Topic/CFrameWndEx::GetDockingManager.md)|검색은 [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) 프레임 창에 대 한 개체.|  
|[CFrameWndEx::GetMenuBar](../Topic/CFrameWndEx::GetMenuBar.md)|메뉴 모음 개체 프레임 창에 연결 하는 포인터를 반환 합니다.|  
|[CFrameWndEx::GetPane](../Topic/CFrameWndEx::GetPane.md)|지정 된 ID가 창으로 포인터를 반환 합니다.|  
|[CFrameWndEx::GetRibbonBar](../Topic/CFrameWndEx::GetRibbonBar.md)|리본 막대 컨트롤 프레임에 대 한 검색합니다.|  
|[CFrameWndEx::GetTearOffBars](../Topic/CFrameWndEx::GetTearOffBars.md)|분리 된 상태에 있는 창 개체를 반환 합니다.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](../Topic/CFrameWndEx::GetToolbarButtonToolTipText.md)|응용 프로그램 도구 모음 단추에 도구 설명이 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::InsertPane](../Topic/CFrameWndEx::InsertPane.md)|창을 도킹 관리자에 등록합니다.|  
|[CFrameWndEx::IsFullScreen](../Topic/CFrameWndEx::IsFullScreen.md)|프레임 창에서 전체 화면 모드 인지 여부를 결정 합니다.|  
|[CFrameWndEx::IsMenuBarAvailable](../Topic/CFrameWndEx::IsMenuBarAvailable.md)|메뉴 모음 개체 포인터가 유효한 지 여부를 결정 합니다.|  
|[CFrameWndEx::IsPointNearDockSite](../Topic/CFrameWndEx::IsPointNearDockSite.md)|지점에서 맞춤 영역에 있는지 여부를 나타냅니다.|  
|[CFrameWndEx::IsPrintPreview](../Topic/CFrameWndEx::IsPrintPreview.md)|프레임 창을 인쇄 미리 보기 모드 인지 여부를 나타냅니다.|  
|[CFrameWndEx::LoadFrame](../Topic/CFrameWndEx::LoadFrame.md)|프레임 창 만들기 및 리소스 로드를 생성 한 후이 메서드를 호출 합니다.|  
|[CFrameWndEx::NegotiateBorderSpace](../Topic/CFrameWndEx::NegotiateBorderSpace.md)|구현 OLE 클라이언트 테두리 협상 합니다.|  
|[CFrameWndEx::OnActivate](../Topic/CFrameWndEx::OnActivate.md)|프레임 워크는 사용자가 입력 하거나 프레임 밖으로 전환 될 때이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnActivateApp](../Topic/CFrameWndEx::OnActivateApp.md)|응용 프로그램 선택 되거나 선택 취소 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnChangeVisualManager](../Topic/CFrameWndEx::OnChangeVisualManager.md)|프레임 변경 비주얼 관리자를 변경 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnClose](../Topic/CFrameWndEx::OnClose.md)|프레임 워크는 프레임을 닫아도이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnCloseDockingPane](../Topic/CFrameWndEx::OnCloseDockingPane.md)|클릭할 때 프레임 워크에 의해 호출 된  **닫기** 도킹 된 창에서 단추.|  
|[CFrameWndEx::OnCloseMiniFrame](../Topic/CFrameWndEx::OnCloseMiniFrame.md)|클릭할 때 프레임 워크에 의해 호출 된  **닫기** 부동 미니 프레임 창에서 단추.|  
|[CFrameWndEx::OnClosePopupMenu](../Topic/CFrameWndEx::OnClosePopupMenu.md)|WM\_DESTROY 메시지는 활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnCmdMsg](../Topic/CFrameWndEx::OnCmdMsg.md)|메시지 디스패치를 명령 합니다.|  
|[CFrameWndEx::OnContextHelp](../Topic/CFrameWndEx::OnContextHelp.md)|프레임 워크에서 호출 컨텍스트를 표시 합니다 도움말 관련.|  
|[CFrameWndEx::OnCreate](../Topic/CFrameWndEx::OnCreate.md)|프레임 워크에서 프레임을 만든 후에 호출 됩니다.|  
|[CFrameWndEx::OnDestroy](../Topic/CFrameWndEx::OnDestroy.md)|프레임이 소멸 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md)|응용 프로그램 메뉴 항목과 연결 된 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnDrawMenuLogo](../Topic/CFrameWndEx::OnDrawMenuLogo.md)|프레임 워크에서 호출 하면는 `CMFCPopupMenu` 프로세스 개체는  [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지.|  
|[CFrameWndEx::OnDWMCompositionChanged](../Topic/CFrameWndEx::OnDWMCompositionChanged.md)|바탕 화면 창 관리자 \(DWM\) 컴포지션 활성화 또는 비활성화 된 경우 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnExitSizeMove](../Topic/CFrameWndEx::OnExitSizeMove.md)|프레임을 이동 또는 크기 조정을 중지 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnGetMinMaxInfo](../Topic/CFrameWndEx::OnGetMinMaxInfo.md)|프레임 창의 치수 제한을 설정 하려면 크기가 조정 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](../Topic/CFrameWndEx::OnIdleUpdateCmdUI.md)|명령 처리 유휴 상태일 때 프레임 표시를 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnLButtonDown](../Topic/CFrameWndEx::OnLButtonDown.md)|마우스 왼쪽된 단추를 누를 때 프레임 워크가이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnLButtonUp](../Topic/CFrameWndEx::OnLButtonUp.md)|왼쪽된 마우스 단추를 놓을 때 프레임 워크가이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](../Topic/CFrameWndEx::OnMenuButtonToolHitTest.md)|프레임 워크에서 호출 하면는 `CMFCToolBarButton` 프로세스 개체는 `WM_NCHITTEST` 메시지.|  
|[CFrameWndEx::OnMenuChar](../Topic/CFrameWndEx::OnMenuChar.md)|프레임 워크에서 해당 메뉴가 표시 되 고 명령에 해당 하지 않는 키를 누를 때 호출 됩니다.|  
|[CFrameWndEx::OnMouseMove](../Topic/CFrameWndEx::OnMouseMove.md)|프레임 워크는 포인터를 이동할 때이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnMoveMiniFrame](../Topic/CFrameWndEx::OnMoveMiniFrame.md)|창 창 이동할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcActivate](../Topic/CFrameWndEx::OnNcActivate.md)|프레임 비클라이언트 영역의 활성 상태 변경을 나타낼 수 그려야 할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcCalcSize](../Topic/CFrameWndEx::OnNcCalcSize.md)|크기와 위치를 클라이언트 영역을 계산 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnNcHitTest](../Topic/CFrameWndEx::OnNcHitTest.md)|프레임 워크에서 마우스 포인터를 이동할 때 또는 마우스 단추를 누르거나 놓을 때 호출 됩니다.|  
|[CFrameWndEx::OnNcMouseMove](../Topic/CFrameWndEx::OnNcMouseMove.md)|비클라이언트 영역에서 포인터를 이동할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcPaint](../Topic/CFrameWndEx::OnNcPaint.md)|비 클라이언트 영역을 그려야 할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnPaneCheck](../Topic/CFrameWndEx::OnPaneCheck.md)|창의 표시 여부를 제어 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnPostPreviewFrame](../Topic/CFrameWndEx::OnPostPreviewFrame.md)|인쇄 미리 보기 모드를 변경 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnPowerBroadcast](../Topic/CFrameWndEx::OnPowerBroadcast.md)|전원 관리 이벤트가 발생 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnSetMenu](../Topic/CFrameWndEx::OnSetMenu.md)|프레임 창의 메뉴를 대체 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnSetPreviewMode](../Topic/CFrameWndEx::OnSetPreviewMode.md)|프레임 인쇄 미리 보기 모드를 설정 하는 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnSetText](../Topic/CFrameWndEx::OnSetText.md)|창의 텍스트를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnShowCustomizePane](../Topic/CFrameWndEx::OnShowCustomizePane.md)|빠른 사용자 지정 하면 프레임 워크에서 호출 창을 활성화 합니다.|  
|[CFrameWndEx::OnShowPanes](../Topic/CFrameWndEx::OnShowPanes.md)|표시 하거나 숨기려면 창 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md)|팝업 메뉴를 사용 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnSize](../Topic/CFrameWndEx::OnSize.md)|프레임 워크는 프레임의 크기가 변경 된 후이 메서드를 호출합니다.|  
|[CFrameWndEx::OnSizing](../Topic/CFrameWndEx::OnSizing.md)|프레임 워크는 사용자가 프레임의 크기가 조정 될 때이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnSysColorChange](../Topic/CFrameWndEx::OnSysColorChange.md)|시스템 색을 변경 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnTearOffMenu](../Topic/CFrameWndEx::OnTearOffMenu.md)|분리 된 막대가 있는 메뉴를 사용 하면 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnToolbarContextMenu](../Topic/CFrameWndEx::OnToolbarContextMenu.md)|컨텍스트 메뉴 도구 모음을 작성 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnToolbarCreateNew](../Topic/CFrameWndEx::OnToolbarCreateNew.md)|프레임 워크는 새 도구 모음을 만들려면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnToolbarDelete](../Topic/CFrameWndEx::OnToolbarDelete.md)|도구 모음을 삭제할 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnUpdateFrameMenu](../Topic/CFrameWndEx::OnUpdateFrameMenu.md)|프레임 메뉴를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnUpdateFrameTitle](../Topic/CFrameWndEx::OnUpdateFrameTitle.md)|프레임 워크는 프레임 창의 제목 표시줄을 업데이트 하려면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnUpdatePaneMenu](../Topic/CFrameWndEx::OnUpdatePaneMenu.md)|창 메뉴 업데이트 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnWindowPosChanged](../Topic/CFrameWndEx::OnWindowPosChanged.md)|창 관리 메서드 호출으로 인해 프레임 크기, 위치 또는 z 축이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::PaneFromPoint](../Topic/CFrameWndEx::PaneFromPoint.md)|지정 된 위치에 있는 도킹 창을 반환 합니다.|  
|[CFrameWndEx::PreTranslateMessage](../Topic/CFrameWndEx::PreTranslateMessage.md)|특정 창 메시지를 디스패치하기 전에 처리 합니다.|  
|[CFrameWndEx::RecalcLayout](../Topic/CFrameWndEx::RecalcLayout.md)|프레임 및 자식 창 레이아웃을 조정합니다.|  
|[CFrameWndEx::RemovePaneFromDockManager](../Topic/CFrameWndEx::RemovePaneFromDockManager.md)|창에 등록이 취소 되 고 내부에 도킹 관리자 목록에서 제거 합니다.|  
|[CFrameWndEx::SetDockState](../Topic/CFrameWndEx::SetDockState.md)|레지스트리에 저장 된 상태로 도킹 도킹 레이아웃을 복원 합니다.|  
|[CFrameWndEx::SetPrintPreviewFrame](../Topic/CFrameWndEx::SetPrintPreviewFrame.md)|프레임 창을 인쇄 미리 보기를 설정합니다.|  
|[CFrameWndEx::SetupToolbarMenu](../Topic/CFrameWndEx::SetupToolbarMenu.md)|사용자 정의 명령을 도구 모음 메뉴에 삽입 합니다.|  
|[CFrameWndEx::ShowFullScreen](../Topic/CFrameWndEx::ShowFullScreen.md)|주 프레임의 전체 화면 모드와 일반 모드 사이 전환합니다.|  
|[CFrameWndEx::ShowPane](../Topic/CFrameWndEx::ShowPane.md)|표시 하거나 지정한 창을 숨깁니다.|  
|[CFrameWndEx::UpdateCaption](../Topic/CFrameWndEx::UpdateCaption.md)|프레임 창의 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::WinHelp](../Topic/CFrameWndEx::WinHelp.md)|하나를 호출 하 여 `WinHelp` 컨텍스트 또는 응용 프로그램 관련 도움말.|  
  
## 예제  
 다음 예제에서는 클래스에서 상속 된 `CFrameWndEx` 클래스.  메서드 시그니처가 서브 클래스 및 재정의 하는 방법의 예제는 `OnShowPopupMenu` 메서드.  이 코드 조각에 속해 있는  [워드 패드 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/CPP/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/CPP/cframewndex-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## 요구 사항  
 **헤더:** afxframewndex.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)