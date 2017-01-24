---
title: "CPaneFrameWnd Class | Microsoft Docs"
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
  - "CPaneFrameWnd.Serialize"
  - "CPaneFrameWnd.PreTranslateMessage"
  - "CPaneFrameWnd"
  - "CPaneFrameWnd::Serialize"
  - "PreTranslateMessage"
  - "CPaneFrameWnd::PreTranslateMessage"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneFrameWnd class"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 하나의 창이 포함된 미니 프레임 창을 구현합니다.  창은 창의 클라이언트 영역을 채웁니다.  
  
## 구문  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)|창을 추가합니다.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](../Topic/CPaneFrameWnd::AddRemovePaneFromGlobalList.md)|전역 목록에서 창을 추가하거나 제거합니다.|  
|[CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)|미니 프레임 창의 레이아웃을 조정합니다.|  
|[CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)||  
|[CPaneFrameWnd::CalcBorderSize](../Topic/CPaneFrameWnd::CalcBorderSize.md)|미니 프레임 창의 테두리 크기를 계산합니다.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)|도킹된 창의 예상 사각형을 계산합니다.|  
|[CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)|현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.|  
|[CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)|미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.|  
|[CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)|창을 탭된 문서로 변환합니다.|  
|[CPaneFrameWnd::Create](../Topic/CPaneFrameWnd::Create.md)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|  
|[CPaneFrameWnd::CreateEx](../Topic/CPaneFrameWnd::CreateEx.md)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|  
|[CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)|창을 도킹합니다.|  
|[CPaneFrameWnd::FindFloatingPaneByID](../Topic/CPaneFrameWnd::FindFloatingPaneByID.md)|부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.|  
|[CPaneFrameWnd::FrameFromPoint](../Topic/CPaneFrameWnd::FrameFromPoint.md)|사용자가 제공한 지점을 포함하는 미니 프레임 창을 찾습니다.|  
|[CPaneFrameWnd::GetCaptionHeight](../Topic/CPaneFrameWnd::GetCaptionHeight.md)|미니 프레임 창 캡션의 높이를 반환합니다.|  
|[CPaneFrameWnd::GetCaptionRect](../Topic/CPaneFrameWnd::GetCaptionRect.md)|미니 프레임 창 캡션의 경계 사각형을 계산합니다.|  
|[CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)|캡션 텍스트를 반환합니다.|  
|[CPaneFrameWnd::GetDockingManager](../Topic/CPaneFrameWnd::GetDockingManager.md)||  
|[CPaneFrameWnd::GetDockingMode](../Topic/CPaneFrameWnd::GetDockingMode.md)|도킹 모드를 반환합니다.|  
|[CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)|미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.|  
|[CPaneFrameWnd::GetHotPoint](../Topic/CPaneFrameWnd::GetHotPoint.md)||  
|[CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)|미니 프레임 창에 포함된 창을 반환합니다.|  
|[CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)|미니 프레임 창에 포함된 창 수를 반환합니다.|  
|[CPaneFrameWnd::GetParent](../Topic/CPaneFrameWnd::GetParent.md)||  
|[CPaneFrameWnd::GetPinState](../Topic/CPaneFrameWnd::GetPinState.md)||  
|[CPaneFrameWnd::GetRecentFloatingRect](../Topic/CPaneFrameWnd::GetRecentFloatingRect.md)||  
|[CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)|미니 프레임 창에 포함된 표시 창 수를 반환합니다.|  
|[CPaneFrameWnd::HitTest](../Topic/CPaneFrameWnd::HitTest.md)|미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.|  
|[CPaneFrameWnd::IsCaptured](../Topic/CPaneFrameWnd::IsCaptured.md)||  
|[CPaneFrameWnd::IsDelayShow](../Topic/CPaneFrameWnd::IsDelayShow.md)||  
|[CPaneFrameWnd::IsRollDown](../Topic/CPaneFrameWnd::IsRollDown.md)|미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.|  
|[CPaneFrameWnd::IsRollUp](../Topic/CPaneFrameWnd::IsRollUp.md)|미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.|  
|[CPaneFrameWnd::KillDockingTimer](../Topic/CPaneFrameWnd::KillDockingTimer.md)|도킹 타이머를 중지합니다.|  
|[CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)|레지스트리에서 창의 상태를 로드합니다.|  
|[CPaneFrameWnd::OnBeforeDock](../Topic/CPaneFrameWnd::OnBeforeDock.md)|도킹 가능한지 여부를 결정합니다.|  
|[CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)|가장 최근 위치에 미니 프레임 창을 도킹합니다.|  
|[CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)|롤업 타이머를 중지합니다.|  
|[CPaneFrameWnd::OnMovePane](../Topic/CPaneFrameWnd::OnMovePane.md)|지정된 오프셋만큼 미니 프레임 창을 이동합니다.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)|포함된 창의 레이아웃을 조정합니다.|  
|[CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)|롤업 타이머를 설정합니다.|  
|[CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)|미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)|미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.|  
|[CPaneFrameWnd::Pin](../Topic/CPaneFrameWnd::Pin.md)||  
|`CPaneFrameWnd::PreTranslateMessage`|창 메시지가 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수로 디스패치되기 전에 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스가 이 메시지를 해석하는 데 사용됩니다.|  
|[CPaneFrameWnd::RedrawAll](../Topic/CPaneFrameWnd::RedrawAll.md)|모든 미니 프레임 창을 다시 그립니다.|  
|[CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)|잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)|미니 프레임 창에서 창을 제거합니다.|  
|[CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)|한 창을 다른 창으로 대체합니다.|  
|[CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)|레지스트리에 창의 상태를 저장합니다.|  
|`CPaneFrameWnd::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.|  
|[CPaneFrameWnd::SetCaptionButtons](../Topic/CPaneFrameWnd::SetCaptionButtons.md)|캡션 단추를 설정합니다.|  
|[CPaneFrameWnd::SetDelayShow](../Topic/CPaneFrameWnd::SetDelayShow.md)||  
|[CPaneFrameWnd::SetDockingManager](../Topic/CPaneFrameWnd::SetDockingManager.md)||  
|[CPaneFrameWnd::SetDockingTimer](../Topic/CPaneFrameWnd::SetDockingTimer.md)|도킹 타이머를 설정합니다.|  
|[CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)|도킹 상태를 설정합니다.|  
|[CPaneFrameWnd::SetHotPoint](../Topic/CPaneFrameWnd::SetHotPoint.md)||  
|[CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)|사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::SizeToContent](../Topic/CPaneFrameWnd::SizeToContent.md)|포함된 창과 크기가 같도록 미니 프레임 창의 크기를 조정합니다.|  
|[CPaneFrameWnd::StartTearOff](../Topic/CPaneFrameWnd::StartTearOff.md)|메뉴를 분리합니다.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)||  
  
### 보호된 메서드  
  
|이름|설명|  
|--------|--------|  
|[CPaneFrameWnd::OnCheckRollState](../Topic/CPaneFrameWnd::OnCheckRollState.md)|미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.|  
|[CPaneFrameWnd::OnDrawBorder](../Topic/CPaneFrameWnd::OnDrawBorder.md)|미니 프레임 창의 테두리를 그립니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CPaneFrameWnd::m\_bUseSaveBits](../Topic/CPaneFrameWnd::m_bUseSaveBits.md)|`CS_SAVEBITS` 클래스 스타일을 사용하여 창 클래스를 등록할지 여부를 지정합니다.|  
  
## 설명  
 창이 도킹된 상태에서 부동 상태로 전환되면 프레임워크에서 자동으로 `CPaneFrameWnd` 개체를 만듭니다.  
  
 내용을 표시\(즉시 도킹\)하거나 끌기 사각형을 사용하여\(표준 도킹\) 미니 프레임 창을 끌 수 있습니다.  미니 프레임 컨테이너 창의 도킹 모드에 따라 미니 프레임의 끌기 동작이 결정됩니다.  자세한 내용은 [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)를 참조하세요.  
  
 미니 프레임 창에 포함된 창 스타일에 따라 캡션에 단추가 표시됩니다.  창을 닫을 수 있는 경우\([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\) 닫기 단추가 표시됩니다.  창에 `AFX_CBRS_AUTO_ROLLUP` 스타일이 있는 경우 핀이 표시됩니다.  
  
 `CPaneFrameWnd`에서 클래스를 파생하는 경우 프레임워크에 만드는 방법을 알려야 합니다.  [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)을 재정의하여 클래스를 만들거나, 클래스에 대한 런타임 클래스 정보를 가리키도록 `CPane::m_pMiniFrameRTC` 멤버를 설정합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
## 요구 사항  
 **헤더:** afxPaneFrameWnd.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)