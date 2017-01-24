---
title: "CDockablePane Class | Microsoft Docs"
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
  - "CDockablePane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePane class"
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockablePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

수 항구 사이트에 도킹 하거나 탭된 창에 포함 된 창을 구현 합니다.  
  
## 구문  
  
```  
class CDockablePane : public CPane  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDockablePane::CDockablePane](../Topic/CDockablePane::CDockablePane.md)|생성 및 초기화는 `CDockablePane` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md)|창을 다른 창으로 연결 됩니다.  창 탭된을 만듭니다.|  
|[CDockablePane::CalcFixedLayout](../Topic/CDockablePane::CalcFixedLayout.md)|창 사각형의 크기를 반환합니다.|  
|[CDockablePane::CanAcceptMiniFrame](../Topic/CDockablePane::CanAcceptMiniFrame.md)|지정 된 미니 프레임 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAcceptPane](../Topic/CDockablePane::CanAcceptPane.md)|다른 창을 현재 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAutoHide](../Topic/CDockablePane::CanAutoHide.md)|창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다.  \(재정의 [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md).\)|  
|[CDockablePane::CanBeAttached](../Topic/CDockablePane::CanBeAttached.md)|현재 창 다른 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md)|도킹 가능한 창을 하나 이상의 탭 MDI 문서를 변환합니다.|  
|[CDockablePane::CopyState](../Topic/CDockablePane::CopyState.md)|도킹 가능 창의 상태를 복사합니다.|  
|[CDockablePane::Create](../Topic/CDockablePane::Create.md)|Windows 컨트롤을 만들고이에 연결 된 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateDefaultPaneDivider](../Topic/CDockablePane::CreateDefaultPaneDivider.md)|프레임 창에 도킹 된 창의 기본 구분선을 만듭니다.|  
|[CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md)|Windows 컨트롤을 만들고이에 연결 된 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateTabbedPane](../Topic/CDockablePane::CreateTabbedPane.md)|탭된 창에는 현재 창에서 만듭니다.|  
|[CDockablePane::DockPaneContainer](../Topic/CDockablePane::DockPaneContainer.md)|컨테이너 창에 도킹합니다.|  
|[CDockablePane::DockPaneStandard](../Topic/CDockablePane::DockPaneStandard.md)|한 창 개요 \(표준\) 도킹을 사용 하 여 도킹 합니다.|  
|`CDockablePane::DockToFrameWindow`|내부적으로 사용됩니다.  도킹 된 창 수 [CPane::DockPane](../Topic/CPane::DockPane.md) 또는 [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md).|  
|[CDockablePane::DockToRecentPos](../Topic/CDockablePane::DockToRecentPos.md)|창에 저장 된 최근 도킹 위치에 도킹합니다.|  
|[CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md)|도킹 창 다른 도킹 창에 도킹합니다.|  
|[CDockablePane::EnableAutohideAll](../Topic/CDockablePane::EnableAutohideAll.md)|자동 숨기기 모드가 창의 다른 창에서 컨테이너와 함께 사용할 수 있거나.|  
|[CDockablePane::EnableGripper](../Topic/CDockablePane::EnableGripper.md)|표시 하거나 캡션 \(그리퍼\)를 숨깁니다.|  
|[CDockablePane::GetAHRestoredRect](../Topic/CDockablePane::GetAHRestoredRect.md)|창에 자동 숨기기 모드로 볼 때 위치를 지정 합니다.|  
|[CDockablePane::GetAHSlideMode](../Topic/CDockablePane::GetAHSlideMode.md)|창 자동 숨기기 슬라이드 모드를 검색합니다.|  
|`CDockablePane::GetAutoHideButton`|내부적으로 사용됩니다.|  
|`CDockablePane::GetAutoHideToolBar`|내부적으로 사용됩니다.|  
|[CDockablePane::GetCaptionHeight](../Topic/CDockablePane::GetCaptionHeight.md)|현재 캡션 높이 반환 합니다.|  
|[CDockablePane::GetDefaultPaneDivider](../Topic/CDockablePane::GetDefaultPaneDivider.md)|기본 컨테이너의 창 틀을 반환합니다.|  
|[CDockablePane::GetDockingStatus](../Topic/CDockablePane::GetDockingStatus.md)|도킹 될 수 있는 창에 제공 된 포인터 위치에 따라 결정 됩니다.|  
|[CDockablePane::GetDragSensitivity](../Topic/CDockablePane::GetDragSensitivity.md)|도킹 창 드래그 민감도 반환합니다.|  
|[CDockablePane::GetLastPercentInPaneContainer](../Topic/CDockablePane::GetLastPercentInPaneContainer.md)|해당 컨테이너 내에서 차지 하는 창 공간의 백분율을 검색 합니다.|  
|[CDockablePane::GetTabArea](../Topic/CDockablePane::GetTabArea.md)|창의 탭 영역을 검색 합니다.|  
|[CDockablePane::GetTabbedPaneRTC](../Topic/CDockablePane::GetTabbedPaneRTC.md)|다른 창에는 현재 창에 도킹 하 고 만든 탭된 창에 대 한 런타임 클래스 정보를 반환 합니다.|  
|[CDockablePane::HasAutoHideMode](../Topic/CDockablePane::HasAutoHideMode.md)|도킹 창을 자동 숨기기 모드로 전환할 수 있습니다 여부를 지정 합니다.|  
|[CDockablePane::HitTest](../Topic/CDockablePane::HitTest.md)|마우스를 클릭할 위치는 창에서 특정 위치를 지정 합니다.|  
|`CDockablePane::IsAccessibilityCompatible`|내부적으로 사용됩니다.|  
|[CDockablePane::IsAutohideAllEnabled](../Topic/CDockablePane::IsAutohideAllEnabled.md)|컨테이너에 있는 다른 모든 창 및 도킹 된 창 자동 숨기기 모드로 배치할 수 있는지 여부를 나타냅니다.|  
|[CDockablePane::IsAutoHideMode](../Topic/CDockablePane::IsAutoHideMode.md)|창 자동 숨기기 모드에 있는지 여부를 결정 합니다.|  
|`CDockablePane::IsChangeState`|내부적으로 사용됩니다.|  
|[CDockablePane::IsDocked](../Topic/CDockablePane::IsDocked.md)|현재 창의 도킹 여부를 결정 합니다.|  
|[CDockablePane::IsHideInAutoHideMode](../Topic/CDockablePane::IsHideInAutoHideMode.md)|이 표시 된 \(숨겨진 호출한 경우\) 자동 숨기기 모드에 있는 창의 동작이 결정 `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](../Topic/CDockablePane::IsInFloatingMultiPaneFrameWnd.md)|다중 창 프레임 창에 창인지 여부를 지정 합니다.|  
|[CDockablePane::IsResizable](../Topic/CDockablePane::IsResizable.md)|창 크기를 조정할 수 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsTabLocationBottom](../Topic/CDockablePane::IsTabLocationBottom.md)|탭 위쪽 또는 아래쪽 창에 있는 지 여부를 지정 합니다.|  
|[CDockablePane::IsTracked](../Topic/CDockablePane::IsTracked.md)|사용자가 창을 끌 여부를 지정 합니다.|  
|[CDockablePane::IsVisible](../Topic/CDockablePane::IsVisible.md)|현재 창에 표시 되는지 여부를 결정 합니다.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/ko-kr/96110136-4f46-4764-8a76-3b4abaf77917)|내부적으로 사용됩니다.|  
|[CDockablePane::OnAfterChangeParent](../Topic/CDockablePane::OnAfterChangeParent.md)|창의 부모가 변경 될 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md).\)|  
|[CDockablePane::OnAfterDockFromMiniFrame](../Topic/CDockablePane::OnAfterDockFromMiniFrame.md)|프레임 창에 도킹 된 부동 모음 도킹 하면 프레임 워크에서 호출 됩니다.|  
|[CDockablePane::OnBeforeChangeParent](../Topic/CDockablePane::OnBeforeChangeParent.md)|부모 창의 변경 하는 경우 프레임 워크에서 호출 됩니다.  \(재정의 [CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md).\)|  
|[CDockablePane::OnBeforeFloat](../Topic/CDockablePane::OnBeforeFloat.md)|창에 대 한 float 될 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](../Topic/CDockablePane::RemoveFromDefaultPaneDividier.md)|프레임 워크는 창 켜져야 되는 경우이 메서드를 호출 합니다.|  
|[CDockablePane::ReplacePane](../Topic/CDockablePane::ReplacePane.md)|지정 된 창에는 창을 대체합니다.|  
|[CDockablePane::RestoreDefaultPaneDivider](../Topic/CDockablePane::RestoreDefaultPaneDivider.md)|프레임 워크의 기본 틀을 복원 하는 창 deserialize 되는이 메서드를 호출 합니다.|  
|`CDockablePane::SaveState`|내부적으로 사용됩니다.|  
|`CDockablePane::Serialize`|창에 serialize합니다.  \(재정의 `CBasePane::Serialize`.\)|  
|[CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|도킹 창을 표시 사이 전환 하 고 자동 숨기기 모드.|  
|[CDockablePane::SetAutoHideParents](../Topic/CDockablePane::SetAutoHideParents.md)|자동 숨기기 단추와 창의 자동 숨기기 도구 모음을 설정합니다.|  
|`CDockablePane::SetDefaultPaneDivider`|내부적으로 사용됩니다.|  
|[CDockablePane::SetLastPercentInPaneContainer](../Topic/CDockablePane::SetLastPercentInPaneContainer.md)|해당 컨테이너 내에서 차지 하는 창 공간의 백분율을 설정 합니다.|  
|`CDockablePane::SetResizeMode`|내부적으로 사용됩니다.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](../Topic/CDockablePane::SetRestoredDefaultPaneDivider.md)|복원 된 기본 틀을 설정 합니다.|  
|[CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md)|두 개의 창이 함께 도킹 하 고 만든 탭된 창에 대 한 런타임 클래스 정보를 설정 합니다.|  
|[CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md)|표시 하거나 창을 숨깁니다.|  
|[CDockablePane::Slide](../Topic/CDockablePane::Slide.md)|표시 하거나 창 창 자동 숨기기 모드에 있는 경우에 표시 됩니다는 애니메이션 슬라이딩을 숨깁니다.|  
|[CDockablePane::ToggleAutoHide](../Topic/CDockablePane::ToggleAutoHide.md)|자동 숨기기 모드로 전환 합니다.  \(재정의 [CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md) .\)|  
|[CDockablePane::UndockPane](../Topic/CDockablePane::UndockPane.md)|창을 주 프레임 창 또는 미니 프레임 창 컨테이너에서 도킹 해제 합니다.|  
|`CDockablePane::UnSetAutoHideMode`|내부적으로 사용됩니다.  자동 숨기기 모드를 설정할 수 있습니다[CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDockablePane::CheckAutoHideCondition](../Topic/CDockablePane::CheckAutoHideCondition.md)|도킹 창 \(자동 숨기기 모드 에서\) 숨길지 여부를 결정 합니다.|  
|[CDockablePane::CheckStopSlideCondition](../Topic/CDockablePane::CheckStopSlideCondition.md)|슬라이딩 자동 숨기기 도킹 창에 중지 시기를 결정 합니다.|  
|[CDockablePane::DrawCaption](../Topic/CDockablePane::DrawCaption.md)|도킹 창 캡션 \(그리퍼\)를 그립니다.|  
|[CDockablePane::OnPressButtons](../Topic/CDockablePane::OnPressButtons.md)|사용자 이외의 다른 캡션 단추를 누를 때 호출 된 `AFX_HTCLOSE` 및 `AFX_HTMAXBUTTON` 단추.|  
|[CDockablePane::OnSlide](../Topic/CDockablePane::OnSlide.md)|창에 표시 하거나 숨길 수 있는 경우 자동 숨기기 슬라이드 효과 렌더링 하는 프레임 워크에서 호출 됩니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md)|도킹 가능한 창 자동 숨김 애니메이션이 비활성 인지 여부를 지정 합니다.|  
|[CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md)|창 자동 숨기기 모드일 때 창의 동작을 결정 합니다.|  
|[CDockablePane::m\_nSlideSteps](../Topic/CDockablePane::m_nSlideSteps.md)|이 때 애니메이션 속도 창의 지정 표시 하거나 숨길 때 자동 숨기기 모드에서.|  
  
## 설명  
 `CDockablePane`다음 기능을 구현합니다.  
  
-   주 프레임 창에 도킹 된 창  
  
-   창 자동 숨기기 모드로 전환 합니다.  
  
-   창 탭된 창에 연결 합니다.  
  
-   미니 프레임 창에는 창 부동.  
  
-   미니 프레임 창에서 부동 상태인 다른 창에 도킹 된 창  
  
-   창 크기를 조정 합니다.  
  
-   로드 및 도킹 창에 상태를 저장 합니다.  
  
    > [!NOTE]
    >  상태 정보는 Windows 레지스트리에 저장 됩니다.  
  
-   창 캡션 유무를 만드는 중입니다.  캡션 텍스트 레이블이 있고 그래디언트 색상으로 채울 수 있습니다.  
  
-   창의 내용을 표시 하는 동안 창에 드래그  
  
-   끌기 사각형을 표시 하는 동안 창을 끌어 옵니다.  
  
 응용 프로그램에서 도킹 창을 사용 하려면 창 클래스에서 파생 된 `CDockablePane` 클래스입니다.  주 프레임 창 개체 또는 window 개체 인스턴스 창 제어 파생된 개체를 포함 합니다.  다음 호출을 [CDockablePane::Create](../Topic/CDockablePane::Create.md) 메서드 또는 [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md) 메서드를 처리 하는 경우는 `WM_CREATE` 주 프레임 창에 메시지를에서.  마지막으로 창 개체를 호출 하 여를 설정 [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md), [CBasePane::DockPane](../Topic/CBasePane::DockPane.md), 또는 [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md).  
  
## 사용자 지정 팁  
 다음 팁을 적용 `CDockablePane` 개체:  
  
-   호출 하는 경우 [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) 두 탭, 도킹 가능한 창이 탭된 창에 대 한 포인터를 반환할는 `ppTabbedControlBar` 매개 변수.  이 매개 변수를 사용 하 여 탭된 창에 탭을 추가할 수 있습니다.  
  
-   종류에 의해 생성 되는 탭된 창 [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) 에 의해 결정 됩니다의 `CDockablePane` 개체에 `pTabControlBarAttachTo` 매개 변수.  호출할 수 있습니다 [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md) 에 설정 탭된 창 종류는 `CDockablePane` 만들어집니다.  기본 형식에 의해 결정 됩니다의 `dwTabbedStyle` 의 [CDockablePane::Create](../Topic/CDockablePane::Create.md) 처음 만들 때의 `CDockablePane`.  경우 `dwTabbedStyle` 는 기본 형식인 AFX\_CBRS\_OUTLOOK\_TABS [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md). 경우 `dwTabbedStyle` 는 기본 형식인 AFX\_CBRS\_REGULAR\_TABS [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
-   도킹 가능한 창 하나를 고정 하려면 호출을 [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md) 메서드.  이 메서드를 호출 하기 전에 원래 창 위치 도킹 해야 합니다.  
  
-   멤버 변수 [CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md) 컨트롤 도킹 가능한 창을 자동으로 작동 하는 방법을 숨기기 모드를 호출 하면 [CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md).  이 멤버 변수를 설정는 경우 `TRUE`, 도킹 가능한 창과 자동 숨기기 단추를 숨길 수 있습니다.  그렇지 않으면, 시작 및 종료 슬라이드 됩니다.  
  
-   애니메이션 자동 숨기기를 설정 하 여 비활성화할 수 있습니다는 [CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md) 멤버 변수 `TRUE`.  
  
## 예제  
 구성 하는 방법 다음 예제는 `CDockablePane` 의 다양 한 메서드를 사용 하 여 개체의 `CDockablePane` 클래스.  도킹 가능한 창에 대 한 모든 기능을 사용 하는 자동 숨기기, 캡션이나 그리퍼를 사용, 자동 숨김 모드를 사용 하도록 설정 및 표시 창에서 자동 숨기기 모드에 있는 창에 애니메이션을 적용 하는 방법을 예제를 보여 줍니다.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/CPP/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/CPP/cdockablepane-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## 요구 사항  
 **헤더:** afxDockablePane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)