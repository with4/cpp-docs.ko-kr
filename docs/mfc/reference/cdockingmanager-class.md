---
title: "CDockingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingManager class"
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CDockingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

주 프레임 창에 도킹 레이아웃을 제어 하는 핵심 기능을 구현 합니다.  
  
## 구문  
  
```  
class CDockingManager : public CObject  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDockingManager::AddDockSite](../Topic/CDockingManager::AddDockSite.md)|도킹 창을 만들고 목록에 컨트롤 막대를 추가 합니다.|  
|[CDockingManager::AddHiddenMDITabbedBar](../Topic/CDockingManager::AddHiddenMDITabbedBar.md)|핸들은 모음에 추가 창에 숨겨진된 MDI 창 표시줄 탭의 목록.|  
|[CDockingManager::AddMiniFrame](../Topic/CDockingManager::AddMiniFrame.md)|미니 프레임은 프레임을 추가합니다.|  
|[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)|창을 도킹 관리자에 등록합니다.|  
|[CDockingManager::AdjustDockingLayout](../Topic/CDockingManager::AdjustDockingLayout.md)|다시 계산 하 고 모든 창 프레임 창에서의 레이아웃을 조정 합니다.|  
|[CDockingManager::AdjustPaneFrames](../Topic/CDockingManager::AdjustPaneFrames.md)|발생의 `WM_NCCALCSIZE` 모든 창에 보낼 메시지와 `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](../Topic/CDockingManager::AdjustRectToClientArea.md)|사각형의 맞춤을 조정 합니다.|  
|[CDockingManager::AlignAutoHidePane](../Topic/CDockingManager::AlignAutoHidePane.md)|도킹 창을 자동 숨기기 모드에 걸리는 전체 너비 또는 높이의 프레임의 클라이언트 영역으로 둘러싸인 도킹 사이트 수 있도록 크기가 조정 됩니다.|  
|[CDockingManager::AutoHidePane](../Topic/CDockingManager::AutoHidePane.md)|자동 숨기기 도구 모음을 만듭니다.|  
|[CDockingManager::BringBarsToTop](../Topic/CDockingManager::BringBarsToTop.md)|지정 된 맞춤 위쪽에 있는 고정된 막대를 표시 합니다.|  
|[CDockingManager::BuildPanesMenu](../Topic/CDockingManager::BuildPanesMenu.md)|도킹 창 및 도구 모음 이름이 메뉴에 추가 합니다.|  
|[CDockingManager::CalcExpectedDockedRect](../Topic/CDockingManager::CalcExpectedDockedRect.md)|도킹 된 창의 예상된 사각형을 계산합니다.|  
|[CDockingManager::Create](../Topic/CDockingManager::Create.md)|도킹 관리자를 만듭니다.|  
|[CDockingManager::DeterminePaneAndStatus](../Topic/CDockingManager::DeterminePaneAndStatus.md)|주어진된 시점 및 도킹 상태를 포함 하는 창으로 결정 합니다.|  
|[CDockingManager::DisableRestoreDockState](../Topic/CDockingManager::DisableRestoreDockState.md)|사용 하거나 레지스트리에서 도킹 레이아웃의 로드를 비활성화 합니다.|  
|[CDockingManager::DockPane](../Topic/CDockingManager::DockPane.md)|창을 다른 창 또는 프레임 창에 도킹합니다.|  
|[CDockingManager::DockPaneLeftOf](../Topic/CDockingManager::DockPaneLeftOf.md)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CDockingManager::EnableAutoHidePanes](../Topic/CDockingManager::EnableAutoHidePanes.md)|활성화를 주 프레임 창에 도킹 도킹 창을 만들고 목록에 컨트롤 막대를 추가 합니다.|  
|[CDockingManager::EnableDocking](../Topic/CDockingManager::EnableDocking.md)|도킹 창 만들고 있습니다에 주 프레임 창에 도킹 합니다.|  
|[CDockingManager::EnableDockSiteMenu](../Topic/CDockingManager::EnableDockSiteMenu.md)|팝업 메뉴에서 모든 도킹 창 캡션 열립니다는 추가 단추가 표시 됩니다.|  
|[CDockingManager::EnablePaneContextMenu](../Topic/CDockingManager::EnablePaneContextMenu.md)|라이브러리 WM\_CONTEXTMENU 메시지를 처리 하 고 마우스 오른쪽 단추를 클릭할 때 응용 프로그램의 도구 모음 및 도킹 창 목록을 가진 특수 한 상황에 맞는 메뉴를 표시 하려면 라이브러리를 지정 합니다.|  
|[CDockingManager::FindDockSite](../Topic/CDockingManager::FindDockSite.md)|검색 막대는 지정 된 위치에 있고 지정 된 맞춤 창.|  
|[CDockingManager::FindDockSiteByPane](../Topic/CDockingManager::FindDockSiteByPane.md)|막대 반환 대상 모음 창 id가 창.|  
|[CDockingManager::FindPaneByID](../Topic/CDockingManager::FindPaneByID.md)|창을에서 지정 된 컨트롤 ID 찾습니다.|  
|[CDockingManager::FixupVirtualRects](../Topic/CDockingManager::FixupVirtualRects.md)|현재 모든 도구 모음 위치를 가상 사각형에 커밋합니다.|  
|[CDockingManager::FrameFromPoint](../Topic/CDockingManager::FrameFromPoint.md)|지정 된 지점이 포함 된 프레임을 반환 합니다.|  
|[CDockingManager::GetClientAreaBounds](../Topic/CDockingManager::GetClientAreaBounds.md)|클라이언트 영역 범위를 포함 하는 사각형을 가져옵니다.|  
|[CDockingManager::GetDockingMode](../Topic/CDockingManager::GetDockingMode.md)|현재 도킹 모드를 반환합니다.|  
|[CDockingManager::GetDockSiteFrameWnd](../Topic/CDockingManager::GetDockSiteFrameWnd.md)|부모 창이 프레임으로 포인터를 가져옵니다.|  
|[CDockingManager::GetEnabledAutoHideAlignment](../Topic/CDockingManager::GetEnabledAutoHideAlignment.md)|창 활성화 맞춤을 반환합니다.|  
|[CDockingManager::GetMiniFrames](../Topic/CDockingManager::GetMiniFrames.md)|미니 컴퓨터의 목록을 가져옵니다.|  
|[CDockingManager::GetOuterEdgeBounds](../Topic/CDockingManager::GetOuterEdgeBounds.md)|프레임의 바깥쪽 가장자리를 포함 하는 사각형을 가져옵니다.|  
|[CDockingManager::GetPaneList](../Topic/CDockingManager::GetPaneList.md)|창 도킹 관리자에 속하는 목록을 반환 합니다.  이 모든 부동 창이 포함 되어 있습니다.|  
|[CDockingManager::GetSmartDockingManager](../Topic/CDockingManager::GetSmartDockingManager.md)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|  
|[CDockingManager::GetSmartDockingManagerPermanent](../Topic/CDockingManager::GetSmartDockingManagerPermanent.md)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|  
|[CDockingManager::GetSmartDockingParams](../Topic/CDockingManager::GetSmartDockingParams.md)|도킹 관리자에 대 한 스마트 도킹 매개 변수를 반환합니다.|  
|[CDockingManager::GetSmartDockingTheme](../Topic/CDockingManager::GetSmartDockingTheme.md)|스마트 도킹 마커를 표시 하는 데 사용 되는 테마를 반환 하는 정적 메서드.|  
|[CDockingManager::HideAutoHidePanes](../Topic/CDockingManager::HideAutoHidePanes.md)|자동 숨기기 모드에 있는 창을 숨깁니다.|  
|[CDockingManager::InsertDockSite](../Topic/CDockingManager::InsertDockSite.md)|도킹 창 만들어 컨트롤 막대의 목록에 삽입 합니다.|  
|[CDockingManager::InsertPane](../Topic/CDockingManager::InsertPane.md)|컨트롤 창의 컨트롤 막대의 목록에 삽입합니다.|  
|[CDockingManager::IsDockSiteMenu](../Topic/CDockingManager::IsDockSiteMenu.md)|팝업 메뉴에서 모든 창의 캡션을 표시할지 여부를 지정 합니다.|  
|[CDockingManager::IsInAdjustLayout](../Topic/CDockingManager::IsInAdjustLayout.md)|모든 창 레이아웃 조정 하는 경우를 결정 합니다.|  
|[CDockingManager::IsOLEContainerMode](../Topic/CDockingManager::IsOLEContainerMode.md)|도킹 관리자 OLE 컨테이너 모드 인지 여부를 지정 합니다.|  
|[CDockingManager::IsPointNearDockSite](../Topic/CDockingManager::IsPointNearDockSite.md)|지정 된 지점을 근처 항구 사이트 인지 확인 합니다.|  
|[CDockingManager::IsPrintPreviewValid](../Topic/CDockingManager::IsPrintPreviewValid.md)|인쇄 미리 보기 모드로 설정 되어 있는지 확인 합니다.|  
|[CDockingManager::LoadState](../Topic/CDockingManager::LoadState.md)|레지스트리에서 관리자의 도킹 상태를 로드합니다.|  
|[CDockingManager::LockUpdate](../Topic/CDockingManager::LockUpdate.md)|지정 된 창에 잠금을 설정합니다.|  
|[CDockingManager::OnActivateFrame](../Topic/CDockingManager::OnActivateFrame.md)|프레임 창을 활성화 해야 비활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CDockingManager::OnClosePopupMenu](../Topic/CDockingManager::OnClosePopupMenu.md)|WM\_DESTROY 메시지는 활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 됩니다.|  
|[CDockingManager::OnMoveMiniFrame](../Topic/CDockingManager::OnMoveMiniFrame.md)|미니 프레임 창 이동 하는 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::OnPaneContextMenu](../Topic/CDockingManager::OnPaneContextMenu.md)|목록 창에 있는 메뉴를 만들 때 프레임 워크에 의해 호출 됩니다.|  
|[CDockingManager::PaneFromPoint](../Topic/CDockingManager::PaneFromPoint.md)|지정 된 지점에 있는 창을 반환 합니다.|  
|[CDockingManager::ProcessPaneContextMenuCommand](../Topic/CDockingManager::ProcessPaneContextMenuCommand.md)|선택 또는 지정 된 명령에 대 한 확인란 선택을 취소 하 고 표시 된 창의 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::RecalcLayout](../Topic/CDockingManager::RecalcLayout.md)|목록 컨트롤에 있는 컨트롤의 내부 레이아웃을 다시 계산합니다.|  
|[CDockingManager::ReleaseEmptyPaneContainers](../Topic/CDockingManager::ReleaseEmptyPaneContainers.md)|빈 창 컨테이너를 해제합니다.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](../Topic/CDockingManager::RemoveHiddenMDITabbedBar.md)|지정한 창 표시줄 숨김 제거 합니다.|  
|[CDockingManager::RemoveMiniFrame](../Topic/CDockingManager::RemoveMiniFrame.md)|미니 프레임 목록에서 지정 된 프레임을 제거합니다.|  
|[CDockingManager::RemovePaneFromDockManager](../Topic/CDockingManager::RemovePaneFromDockManager.md)|창에 등록을 취소 하 고 도킹 관리자에서 목록에서 제거.|  
|[CDockingManager::ReplacePane](../Topic/CDockingManager::ReplacePane.md)|한 창 다른 대체합니다.|  
|[CDockingManager::ResortMiniFramesForZOrder](../Topic/CDockingManager::ResortMiniFramesForZOrder.md)|프레임 미니 프레임 목록을 작성 합니다.|  
|[CDockingManager::SaveState](../Topic/CDockingManager::SaveState.md)|관리자의 도킹 상태를 레지스트리에 저장합니다.|  
|[CDockingManager::SendMessageToMiniFrames](../Topic/CDockingManager::SendMessageToMiniFrames.md)|모든 미니 프레임에 지정 된 메시지를 보냅니다.|  
|[CDockingManager::Serialize](../Topic/CDockingManager::Serialize.md)|도킹 관리자 보관 저장소에 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CDockingManager::SetAutohideZOrder](../Topic/CDockingManager::SetAutohideZOrder.md)|크기, 너비 및 높이 컨트롤 막대 및 지정 된 창에 설정합니다.|  
|[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md)|도킹 모드를 설정합니다.|  
|[CDockingManager::SetDockState](../Topic/CDockingManager::SetDockState.md)|미니 프레임, 자동 숨기기 막대 컨트롤 막대 도킹 상태를 설정합니다.|  
|[CDockingManager::SetPrintPreviewMode](../Topic/CDockingManager::SetPrintPreviewMode.md)|인쇄 미리 보기에 표시 되는 막대의 인쇄 미리 보기 모드를 설정 합니다.|  
|[CDockingManager::SetSmartDockingParams](../Topic/CDockingManager::SetSmartDockingParams.md)|스마트 도킹의 동작을 정의 하는 매개 변수를 설정 합니다.|  
|[CDockingManager::ShowDelayShowMiniFrames](../Topic/CDockingManager::ShowDelayShowMiniFrames.md)|표시 하거나 미니 프레임 창을 숨깁니다.|  
|[CDockingManager::ShowPanes](../Topic/CDockingManager::ShowPanes.md)|표시 하거나 창 자동 숨기기 및 컨트롤 막대를 숨깁니다.|  
|[CDockingManager::StartSDocking](../Topic/CDockingManager::StartSDocking.md)|지정한 창의 스마트 도킹 관리자의 맞춤에 따라 스마트 도킹을 시작 합니다.|  
|[CDockingManager::StopSDocking](../Topic/CDockingManager::StopSDocking.md)|도킹 위치를 스마트.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDockingManager::m\_bHideDockingBarsInContainerMode](../Topic/CDockingManager::m_bHideDockingBarsInContainerMode.md)|OLE 컨테이너 모드에서 창을 숨기는 도킹 관리자 여부를 지정 합니다.|  
|[CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md)|글로벌 도킹 모드를 지정합니다.|  
|[CDockingManager::m\_nDockSensitivity](../Topic/CDockingManager::m_nDockSensitivity.md)|도킹 민감도 지정합니다.|  
|[CDockingManager::m\_nTimeOutBeforeDockingBarDock](../Topic/CDockingManager::m_nTimeOutBeforeDockingBarDock.md)|도킹 창을 즉시 도킹 모드에서 도킹 하기 전에 시간을 밀리초 단위로 지정 합니다.|  
|[CDockingManager::m\_nTimeOutBeforeToolBarDock](../Topic/CDockingManager::m_nTimeOutBeforeToolBarDock.md)|주 프레임 창에 도구 모음 도킹 하기 전에 시간을 밀리초 단위로 지정 합니다.|  
  
## 설명  
 주 프레임 창을 만들고이 클래스를 자동으로 초기화 합니다.  
  
 도킹 관리자 개체를 보유 하 여 도킹 레이아웃에 있는 모든 창 목록 및 모든  [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 주 프레임 창에 속하는 windows.  
  
 `CDockingManager` 클래스 구현 검색 창에 사용할 수 있는 일부 서비스 또는 `CPaneFrameWnd` 창.  주 프레임 창 개체의 줄로 표시 하기 때문에 일반적으로 이러한 서비스 직접 호출 하지 마십시오.  자세한 내용은 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)를 참조하십시오.  
  
## 사용자 지정 팁  
 다음 팁을 적용 `CDockingManager` 개체:  
  
-   [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md)이러한 도킹 모드를 지원합니다.  
  
    -   `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    -   `AFX_DOCK_TYPE::DT_STANDARD`  
  
    -   `AFX_DOCK_TYPE::DT_SMART`  
  
     이러한 도킹 모드에서 정의 된 [CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md) 를 호출 하 여 설정 하 고 [CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md).  
  
-   이동식, 비\-크기 조정 가능한 창에서 만들려는 경우 호출 된 [CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md) 메서드.  창의 레이아웃을 담당 하는 도킹 관리자 창에서이 메서드를 등록 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CDockingManager` 클래스를 구성 하는 `CDockingManager` 개체입니다.  단추도 추가로 여는 팝업 메뉴에서 모든 도킹 창 캡션 표시 하는 방법 및 개체의 도킹 모드를 설정 하는 예제입니다.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/CPP/cdockingmanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxDockingManager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)