---
title: "CMDIFrameWndEx 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWndEx.AddDockSite"
  - "CMDIFrameWndEx"
  - "CMDIFrameWndEx::AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWndEx 클래스"
ms.assetid: dbcafcb3-9a7a-4f11-9dfe-ba57565c81d0
caps.latest.revision: 42
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CMDIFrameWndEx 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기능을 확장  [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md), Windows 다중 문서 인터페이스 \(MDI\) 프레임 창입니다.  
  
## 구문  
  
```  
class CMDIFrameWndEx : public CMDIFrameWnd  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMDIFrameWndEx::ActiveItemRecalcLayout](../Topic/CMDIFrameWndEx::ActiveItemRecalcLayout.md)|활성 항목의 레이아웃을 다시 계산합니다.|  
|`CMDIFrameWndEx::AddDockSite`|이 메서드가 사용되지 않습니다.|  
|[CMDIFrameWndEx::AddPane](../Topic/CMDIFrameWndEx::AddPane.md)|창 도킹 관리자에 등록합니다.|  
|[CMDIFrameWndEx::AdjustClientArea](../Topic/CMDIFrameWndEx::AdjustClientArea.md)|테두리를 허용 하도록 클라이언트 영역을 줄일 수 있습니다.|  
|[CMDIFrameWndEx::AdjustDockingLayout](../Topic/CMDIFrameWndEx::AdjustDockingLayout.md)|모든 도킹 된 창 레이아웃을 다시 계산합니다.|  
|[CMDIFrameWndEx::AreMDITabs](../Topic/CMDIFrameWndEx::AreMDITabs.md)|MDI 탭 기능 또는 MDI 탭 그룹 기능 사용 여부를 결정 합니다.|  
|[CMDIFrameWndEx::CanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::CanCovertControlBarToMDIChild.md)|프레임 창의 도킹 창 탭된 문서를 변환할 수 있는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::ControlBarToTabbedDocument](../Topic/CMDIFrameWndEx::ControlBarToTabbedDocument.md)|지정 된 도킹 창 탭된 문서로 변환합니다.|  
|[CMDIFrameWndEx::CreateDocumentWindow](../Topic/CMDIFrameWndEx::CreateDocumentWindow.md)|자식 문서 창이 만들어집니다.|  
|[CMDIFrameWndEx::CreateNewWindow](../Topic/CMDIFrameWndEx::CreateNewWindow.md)|새 창을 만들려면 프레임 워크에 의해 호출 됩니다.|  
|`CMDIFrameWndEx::CreateObject`|프레임 워크에 의해 이와 같은 클래스의 동적 인스턴스를 만드는 데 사용 합니다.|  
|[CMDIFrameWndEx::DockPane](../Topic/CMDIFrameWndEx::DockPane.md)|지정 된 창 프레임 창에 도킹합니다.|  
|[CMDIFrameWndEx::DockPaneLeftOf](../Topic/CMDIFrameWndEx::DockPaneLeftOf.md)|한 창이 다른 창의 왼쪽에 도킹합니다.|  
|[CMDIFrameWndEx::EnableAutoHidePanes](../Topic/CMDIFrameWndEx::EnableAutoHidePanes.md)|수 있도록 자동 모드 창에 컨트롤이 지정 된 부분의 주 프레임 창에 도킹 된 경우 숨김.|  
|[CMDIFrameWndEx::EnableDocking](../Topic/CMDIFrameWndEx::EnableDocking.md)|MDI 프레임 창에 속하는 창의 도킹 활성화|  
|[CMDIFrameWndEx::EnableFullScreenMainMenu](../Topic/CMDIFrameWndEx::EnableFullScreenMainMenu.md)|표시 하거나 전체 화면 모드에서 기본 메뉴를 숨깁니다.|  
|[CMDIFrameWndEx::EnableFullScreenMode](../Topic/CMDIFrameWndEx::EnableFullScreenMode.md)|프레임 창에 대한 전체 화면 모드를 활성화 합니다.|  
|[CMDIFrameWndEx::EnableLoadDockState](../Topic/CMDIFrameWndEx::EnableLoadDockState.md)|사용 하거나 도킹 상태 로드를 비활성화 합니다.|  
|[CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md)|MDI 탭 그룹 기능을 사용할 수 있거나.|  
|[CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)|MDI 탭 기능을 사용할 수 있거나.  프레임 창이 활성화 되 면 각 MDI 자식 창에 대한 탭을 표시 합니다.|  
|[CMDIFrameWndEx::EnableMDITabsLastActiveActivation](../Topic/CMDIFrameWndEx::EnableMDITabsLastActiveActivation.md)|사용자가 현재 탭을 닫을 때 마지막 활성 탭 활성화 해야 하는지 여부를 지정 합니다.|  
|[CMDIFrameWndEx::EnablePaneMenu](../Topic/CMDIFrameWndEx::EnablePaneMenu.md)|자동 생성 및 관리 창 응용 프로그램의 목록을 표시 하는 팝업 창 메뉴를 사용할 수 있거나.  .|  
|[CMDIFrameWndEx::EnableWindowsDialog](../Topic/CMDIFrameWndEx::EnableWindowsDialog.md)|명령 ID를 호출 하 여 메뉴 항목을 삽입 한  [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자.|  
|[CMDIFrameWndEx::GetActivePopup](../Topic/CMDIFrameWndEx::GetActivePopup.md)|현재 표시 되는 팝업 메뉴에 대한 포인터를 반환합니다.|  
|[CMDIFrameWndEx::GetPane](../Topic/CMDIFrameWndEx::GetPane.md)|지정 된 컨트롤 ID가 창에 대한 포인터를 반환|  
|[CMDIFrameWndEx::GetDefaultResId](../Topic/CMDIFrameWndEx::GetDefaultResId.md)|MDI 프레임 창의 공유 리소스의 ID를 반환합니다.|  
|[CMDIFrameWndEx::GetMDITabGroups](../Topic/CMDIFrameWndEx::GetMDITabGroups.md)|Windows MDI 목록 탭을 반환 합니다.|  
|[CMDIFrameWndEx::GetMDITabs](../Topic/CMDIFrameWndEx::GetMDITabs.md)|밑줄된 탭된 창에 대한 참조를 반환합니다.|  
|[CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems](../Topic/CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems.md)|MDI 탭 그룹 기능을 사용 하면 어떤 상황에 맞는 메뉴 항목을 사용할 수를 결정 하는 플래그의 조합을 반환 합니다.|  
|[CMDIFrameWndEx::GetMenuBar](../Topic/CMDIFrameWndEx::GetMenuBar.md)|메뉴 모음 개체 프레임 창에 연결 하는 포인터를 반환 합니다.|  
|[CMDIFrameWndEx::GetRibbonBar](../Topic/CMDIFrameWndEx::GetRibbonBar.md)|리본 막대 컨트롤 프레임에 대한 검색합니다.|  
|[CMDIFrameWndEx::GetTearOffBars](../Topic/CMDIFrameWndEx::GetTearOffBars.md)|목록을 반환  [CPane](../../mfc/reference/cpane-class.md)\-분리 된 상태에 있는 개체를 파생 합니다.|  
|`CMDIFrameWndEx::GetThisClass`|에 대한 포인터를 얻을 수 있는 프레임 워크에서 호출 된  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMDIFrameWndEx::GetToolbarButtonToolTipText](../Topic/CMDIFrameWndEx::GetToolbarButtonToolTipText.md)|응용 프로그램 도구 모음 단추에 대한 도구 설명이 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::InsertPane](../Topic/CMDIFrameWndEx::InsertPane.md)|지정한 창을 도킹 관리자에 등록합니다.|  
|[CMDIFrameWndEx::IsFullScreen](../Topic/CMDIFrameWndEx::IsFullScreen.md)|프레임 창은 전체 화면 모드 인지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::IsMDITabbedGroup](../Topic/CMDIFrameWndEx::IsMDITabbedGroup.md)|MDI 탭 그룹 기능을 사용할지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::IsMemberOfMDITabGroup](../Topic/CMDIFrameWndEx::IsMemberOfMDITabGroup.md)|지정 된 탭된 창 windows MDI 탭 그룹에 있는 목록에 있는지 확인 합니다.|  
|[CMDIFrameWndEx::IsMenuBarAvailable](../Topic/CMDIFrameWndEx::IsMenuBarAvailable.md)|프레임 창의 메뉴 모음을 있는지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::IsPointNearDockSite](../Topic/CMDIFrameWndEx::IsPointNearDockSite.md)|지정 된 지점 근처 항구 사이트 인지 확인 합니다.|  
|[CMDIFrameWndEx::IsPrintPreview](../Topic/CMDIFrameWndEx::IsPrintPreview.md)|프레임 창을 인쇄 미리 보기 모드에 있는지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::LoadFrame](../Topic/CMDIFrameWndEx::LoadFrame.md)|프레임 창에서 자원 정보를 만듭니다.  \(재정의 `CMDIFrameWnd::LoadFrame`.\)|  
|[CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md)|MDI 탭 그룹의 레이아웃을 지정된 하 고 이전에 열었던된 문서 목록을 로드합니다.|  
|[CMDIFrameWndEx::MDITabMoveToNextGroup](../Topic/CMDIFrameWndEx::MDITabMoveToNextGroup.md)|활성 탭의 현재 활성 탭된 창에서 다음 또는 이전 탭된 그룹으로 이동합니다.|  
|[CMDIFrameWndEx::MDITabNewGroup](../Topic/CMDIFrameWndEx::MDITabNewGroup.md)|단일 창에 있는 새로운 탭된 그룹을 만듭니다.|  
|[CMDIFrameWndEx::NegotiateBorderSpace](../Topic/CMDIFrameWndEx::NegotiateBorderSpace.md)|OLE 현재 위치에서 활성화 하는 동안 프레임 창에서 테두리 공간을 협상합니다.|  
|[CMDIFrameWndEx::OnCloseDockingPane](../Topic/CMDIFrameWndEx::OnCloseDockingPane.md)|클릭할 때 프레임 워크에 의해 호출 된  **닫기** 는 도킹 가능한 창에서 단추.|  
|[CMDIFrameWndEx::OnCloseMiniFrame](../Topic/CMDIFrameWndEx::OnCloseMiniFrame.md)|클릭할 때 프레임 워크에 의해 호출 된  **닫기** 부동 미니 프레임 창에서 단추.|  
|[CMDIFrameWndEx::OnClosePopupMenu](../Topic/CMDIFrameWndEx::OnClosePopupMenu.md)|활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 된 `WM_DESTROY` 메시지.|  
|[CMDIFrameWndEx::OnCmdMsg](../Topic/CMDIFrameWndEx::OnCmdMsg.md)|경로 및 명령 메시지를 발송 하 고 명령 사용자 인터페이스 개체 업데이트 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::OnDrawMenuImage](../Topic/CMDIFrameWndEx::OnDrawMenuImage.md)|메뉴 항목과 연결 된 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnDrawMenuLogo](../Topic/CMDIFrameWndEx::OnDrawMenuLogo.md)|프레임 워크에서 호출 하면는  [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)프로세스는 `WM_PAINT` 메시지.|  
|[CMDIFrameWndEx::OnEraseMDIClientBackground](../Topic/CMDIFrameWndEx::OnEraseMDIClientBackground.md)|MDI 프레임 때 창 프로세스 프레임 워크에 의해 호출 된 `WM_ERASEBKGND` 메시지.|  
|[CMDIFrameWndEx::OnMenuButtonToolHitTest](../Topic/CMDIFrameWndEx::OnMenuButtonToolHitTest.md)|프레임 워크에서 호출 하면는  [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)프로세스 개체는 `WM_NCHITTEST` 메시지.|  
|[CMDIFrameWndEx::OnMoveMiniFrame](../Topic/CMDIFrameWndEx::OnMoveMiniFrame.md)|미니 프레임 창을 이동 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::OnSetPreviewMode](../Topic/CMDIFrameWndEx::OnSetPreviewMode.md)|응용 프로그램의 주 프레임 창을 인쇄 미리 보기 모드를 설정합니다.  \(재정의 [CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md).\)|  
|[CMDIFrameWndEx::OnShowCustomizePane](../Topic/CMDIFrameWndEx::OnShowCustomizePane.md)|빠른 실행을 사용자 지정 하는 창이 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnShowMDITabContextMenu](../Topic/CMDIFrameWndEx::OnShowMDITabContextMenu.md)|상황에 맞는 메뉴 탭 중 하나에 표시 해야 하는 경우 프레임 워크에 의해 호출 됩니다.  \(올바른 MDI 그룹에만 탭에 대한 합니다.\)|  
|[CMDIFrameWndEx::OnShowPanes](../Topic/CMDIFrameWndEx::OnShowPanes.md)|표시 하거나 숨기려면 창 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnShowPopupMenu](../Topic/CMDIFrameWndEx::OnShowPopupMenu.md)|팝업 메뉴가 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnSizeMDIClient](../Topic/CMDIFrameWndEx::OnSizeMDIClient.md)|MDI 클라이언트 창의 크기를 변경할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnTearOffMenu](../Topic/CMDIFrameWndEx::OnTearOffMenu.md)|분리 된 막대가 있는 메뉴 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnUpdateFrameMenu](../Topic/CMDIFrameWndEx::OnUpdateFrameMenu.md)|프레임 메뉴를 업데이트 하는 프레임 워크에서 호출 됩니다.  \(재정의 `CMDIFrameWnd::OnUpdateFrameMenu`.\)|  
|[CMDIFrameWndEx::PaneFromPoint](../Topic/CMDIFrameWndEx::PaneFromPoint.md)|지정 된 지점이 들어 있는 도킹 창을 반환 합니다.|  
|`CMDIFrameWndEx::PreTranslateMessage`|클래스에 의해 사용 되는  [CWinApp](../../mfc/reference/cwinapp-class.md) 창 메시지를 디스패치하기 전에 변환 하는  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수.  \(재정의 `CMDIFrameWnd::PreTranslateMessage`.\)|  
|[CMDIFrameWndEx::RecalcLayout](../Topic/CMDIFrameWndEx::RecalcLayout.md)|프레임 창의 레이아웃을 다시 계산 하도록 프레임 워크에 의해 호출 됩니다.  \(재정의 [CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md).\)|  
|[CMDIFrameWndEx::RemovePaneFromDockManager](../Topic/CMDIFrameWndEx::RemovePaneFromDockManager.md)|창 등록을 취소 하 고 도킹 관리자에서 제거.|  
|[CMDIFrameWndEx::SaveMDIState](../Topic/CMDIFrameWndEx::SaveMDIState.md)|MDI 탭 그룹에서 현재 레이아웃과 이전에 열었던된 문서 목록을 저장합니다.|  
|[CMDIFrameWndEx::SetPrintPreviewFrame](../Topic/CMDIFrameWndEx::SetPrintPreviewFrame.md)|프레임 창을 인쇄 미리 보기를 설정합니다.|  
|[CMDIFrameWndEx::SetupToolbarMenu](../Topic/CMDIFrameWndEx::SetupToolbarMenu.md)|더미 항목을 검색 하 고 지정 된 사용자 정의 항목을 대체 하 여 도구 모음 개체를 수정 합니다.|  
|[CMDIFrameWndEx::ShowFullScreen](../Topic/CMDIFrameWndEx::ShowFullScreen.md)|주 프레임 일반 모드에서 전체 화면 모드로 전환합니다.|  
|[CMDIFrameWndEx::ShowPane](../Topic/CMDIFrameWndEx::ShowPane.md)|표시 하거나 지정한 창을 숨깁니다.|  
|[CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)|만들고 있는  [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 상자 하 고 엽니다.|  
|[CMDIFrameWndEx::TabbedDocumentToControlBar](../Topic/CMDIFrameWndEx::TabbedDocumentToControlBar.md)|도킹 창에 지정 된 탭된 문서를 변환합니다.|  
|[CMDIFrameWndEx::UpdateCaption](../Topic/CMDIFrameWndEx::UpdateCaption.md)|프레임 창의 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::UpdateMDITabbedBarsIcons](../Topic/CMDIFrameWndEx::UpdateMDITabbedBarsIcons.md)|각 MDI 탭된 창에 대한 아이콘을 설정합니다.|  
|[CMDIFrameWndEx::WinHelp](../Topic/CMDIFrameWndEx::WinHelp.md)|WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::WinHelp](../Topic/CWnd::WinHelp.md).\)|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMDIFrameWndEx::m\_bCanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild.md)|도킹 창 MDI 자식 창으로 변환할 수 있는지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::m\_bDisableSetRedraw](../Topic/CMDIFrameWndEx::m_bDisableSetRedraw.md)|MDI 자식 창에 대한 다시 그리기 최적화를 사용할 수 있습니다.|  
  
## 설명  
 MDI 응용 프로그램에서 확장 된 사용자 지정 기능을 활용 하려면 MDI 프레임 창 클래스는 응용 프로그램에서 파생 된 `CMDIFrameWndEx` 대신 `CMDIFrameWnd`.  
  
## 예제  
 다음 예제에서는 클래스에서 파생 된 `CMDIFrameWndEx`.  이 코드에서 제공 되는  [DrawClient 샘플: MFC Ribbon\-Based OLE 개체 그리기 응용 프로그램](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#1](../../mfc/reference/codesnippet/CPP/cmdiframewndex-class_1.h)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)  
  
 [구식이](../../mfc/reference/cmdiframewndex-class.md)  
  
## 요구 사항  
 **헤더:** afxMDIFrameWndEx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWndEx 클래스](../../mfc/reference/cmdichildwndex-class.md)