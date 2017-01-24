---
title: "CPane Class | Microsoft Docs"
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
  - "CPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPane class"
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPane` 클래스의 향상 되는 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md).  기존 MFC 프로젝트를 업그레이드 하는 경우 모두 대체 `CControlBar` 와 `CPane`.  
  
## 구문  
  
```  
class CPane : public CBasePane  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CPane::~CPane`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md)|즉시의 창 레이아웃을 다시 계산합니다.|  
|[CPane::AllocElements](../Topic/CPane::AllocElements.md)|내부 사용에 대 한 저장소를 할당합니다.|  
|[CPane::AllowShowOnPaneMenu](../Topic/CPane::AllowShowOnPaneMenu.md)|런타임에 생성 된 응용 프로그램에 대 한 목록에서 창에 나열 되어 있는지를 지정 합니다.|  
|[CPane::CalcAvailableSize](../Topic/CPane::CalcAvailableSize.md)|지정 된 사각형 및 현재 창 사각형 사이의 크기 차이 계산합니다.|  
|[CPane::CalcInsideRect](../Topic/CPane::CalcInsideRect.md)|내부 계산 사각형은 창의 테두리 및 grippers 고려 합니다.|  
|[CPane::CalcRecentDockedRect](../Topic/CPane::CalcRecentDockedRect.md)|최근에 도킹 된 사각형을 계산합니다.|  
|[CPane::CalcSize](../Topic/CPane::CalcSize.md)|창의 크기를 계산합니다.|  
|[CPane::CanBeDocked](../Topic/CPane::CanBeDocked.md)|지정한 기본 창에는 창 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CPane::CanBeTabbedDocument](../Topic/CPane::CanBeTabbedDocument.md)|창 탭된 문서로 변환할 수 있는지 확인 합니다.|  
|[CPane::ConvertToTabbedDocument](../Topic/CPane::ConvertToTabbedDocument.md)|도킹 가능한 창이 탭된 문서로 변환합니다.|  
|[CPane::CopyState](../Topic/CPane::CopyState.md)|상태 창에 복사합니다.  \(재정의 [CBasePane::CopyState](../Topic/CBasePane::CopyState.md).\)|  
|[CPane::Create](../Topic/CPane::Create.md)|컨트롤 막대를 만들고 연결 하는 `CPane` 개체입니다.|  
|[CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)|부동 창은 미니 프레임 창을 만듭니다.|  
|[CPane::CreateEx](../Topic/CPane::CreateEx.md)|컨트롤 막대를 만들고 연결 하는 `CPane` 개체입니다.|  
|`CPane::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CPane::DockByMouse](../Topic/CPane::DockByMouse.md)|창을 도킹 메서드는 마우스를 사용 하 여 도킹 합니다.|  
|[CPane::DockPane](../Topic/CPane::DockPane.md)|부동 창의 기본 창에 도킹합니다.|  
|[CPane::DockPaneStandard](../Topic/CPane::DockPaneStandard.md)|한 창 개요 \(표준\) 도킹을 사용 하 여 도킹 합니다.|  
|[CPane::DockToFrameWindow](../Topic/CPane::DockToFrameWindow.md)|도킹 가능한 창 프레임에 도킹합니다.  \(재정의 `CBasePane::DockToFrameWindow`.\)|  
|[CPane::DoesAllowSiblingBars](../Topic/CPane::DoesAllowSiblingBars.md)|다른 창을 현재 창 위치 도킹 된 같은 행에 고정할 수 있는지 여부를 나타냅니다.|  
|[CPane::FloatPane](../Topic/CPane::FloatPane.md)|창에 표시 됩니다.|  
|[CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)|양, 창 수 픽셀 단위로 반환 합니다.|  
|[CPane::GetAvailableStretchSize](../Topic/CPane::GetAvailableStretchSize.md)|양, 창 축소 있습니다 픽셀 단위로 반환 합니다.|  
|[CPane::GetBorders](../Topic/CPane::GetBorders.md)|창 테두리의 너비를 반환합니다.|  
|[CPane::GetClientHotSpot](../Topic/CPane::GetClientHotSpot.md)|반환 된  *핫 스폿* 창.|  
|[CPane::GetDockSiteRow](../Topic/CPane::GetDockSiteRow.md)|창 도킹에 도킹 행을 반환 합니다.|  
|[CPane::GetExclusiveRowMode](../Topic/CPane::GetExclusiveRowMode.md)|단독 행 모드로 창인지 여부를 결정 합니다.|  
|[CPane::GetHotSpot](../Topic/CPane::GetHotSpot.md)|원본에 저장 된 핫 스폿을 반환 `CMFCDragFrameImpl` 개체입니다.|  
|[CPane::GetMinSize](../Topic/CPane::GetMinSize.md)|창의 크기를 허용 되는 최소값을 검색 합니다.|  
|[CPane::GetPaneName](../Topic/CPane::GetPaneName.md)|창의 제목을 검색합니다.|  
|`CPane::GetResizeStep`|내부적으로 사용됩니다.|  
|`CPane::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CPane::GetVirtualRect](../Topic/CPane::GetVirtualRect.md)|검색 된  *가상 사각형* 창.|  
|[CPane::IsChangeState](../Topic/CPane::IsChangeState.md)|창 이동할 때이 방법을 다른 창, 고정 행 및 미니 프레임 창, 창 위치를 분석 하 고 적절 한 반환 `AFX_CS_STATUS` 값입니다.|  
|[CPane::IsDragMode](../Topic/CPane::IsDragMode.md)|창 끌 여부를 지정 합니다.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](../Topic/CPane::IsInFloatingMultiPaneFrameWnd.md)|다중 창 프레임 창에 창인지 여부를 지정 합니다.  \(재정의 `CBasePane::IsInFloatingMultiPaneFrameWnd`.\)|  
|[CPane::IsLeftOf](../Topic/CPane::IsLeftOf.md)|창 \(또는 위에\)에 둘지를 결정 하는 지정 된 사각형.|  
|[CPane::IsResizable](../Topic/CPane::IsResizable.md)|창 크기를 조정할 수 있는지 여부를 결정 합니다.  \(재정의 [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md).\)|  
|[CPane::IsTabbed](../Topic/CPane::IsTabbed.md)|창 탭 컨트롤의 탭된 창에 삽입 된 여부를 결정 합니다.  \(재정의 [CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md).\)|  
|[CPane::LoadState](../Topic/CPane::LoadState.md)|창의 상태를 로드합니다.  \(재정의 [CBasePane::LoadState](../Topic/CBasePane::LoadState.md).\)|  
|[CPane::MoveByAlignment](../Topic/CPane::MoveByAlignment.md)|창과 가상 사각형을 지정 된 양만큼 이동합니다.|  
|[CPane::MovePane](../Topic/CPane::MovePane.md)|창에는 지정 된 사각형을 이동합니다.|  
|[CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md)|창의 부모가 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md)|부모 창의 변경 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CPane::OnPressCloseButton](../Topic/CPane::OnPressCloseButton.md)|사용자가 캡션 창에서 닫기 단추를 선택 하면 프레임 워크에서 호출 됩니다.|  
|`CPane::OnProcessDblClk`|내부적으로 사용됩니다.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|특수 창 메뉴 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)|특수 창 메뉴 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|`CPane::PrepareToDock`|내부적으로 사용됩니다.|  
|[CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)|창 레이아웃 정보가 다시 계산 됩니다.  \(재정의 [CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md).\)|  
|[CPane::SaveState](../Topic/CPane::SaveState.md)|창의 상태를 레지스트리에 저장합니다.  \(재정의 [CBasePane::SaveState](../Topic/CBasePane::SaveState.md).\)|  
|[CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md)|활성 창을 표시합니다.|  
|[CPane::SetBorders](../Topic/CPane::SetBorders.md)|창의 테두리 값을 설정합니다.|  
|[CPane::SetClientHotSpot](../Topic/CPane::SetClientHotSpot.md)|창의 핫스폿 설정합니다.|  
|[CPane::SetDockState](../Topic/CPane::SetDockState.md)|도킹 된 창에 대 한 상태 정보를 복원 합니다.|  
|[CPane::SetExclusiveRowMode](../Topic/CPane::SetExclusiveRowMode.md)|사용 하거나 단독으로 행 모드를 해제 합니다.|  
|[CPane::SetMiniFrameRTC](../Topic/CPane::SetMiniFrameRTC.md)|기본 미니 프레임 창에 대 한 런타임 클래스 정보를 설정합니다.|  
|[CPane::SetMinSize](../Topic/CPane::SetMinSize.md)|창의 크기를 허용 되는 최소값을 설정 합니다.|  
|[CPane::SetVirtualRect](../Topic/CPane::SetVirtualRect.md)|집합의  *가상 사각형* 창.|  
|[CPane::StretchPaneDeferWndPos](../Topic/CPane::StretchPaneDeferWndPos.md)|세로 나 가로로 도킹 스타일에 따라 창을 늘어납니다.|  
|[CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md)|자동 숨기기 모드로 전환 합니다.|  
|[CPane::UndockPane](../Topic/CPane::UndockPane.md)|창 도킹 사이트, 기본 슬라이더 또는 미니 프레임 창의 도킹 된 현재에서 제거 합니다.  \(재정의 [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).\)|  
|[CPane::UpdateVirtualRect](../Topic/CPane::UpdateVirtualRect.md)|가상 사각형을 업데이트합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPane::OnAfterDock](../Topic/CPane::OnAfterDock.md)|창에 도킹 되어 있는 경우 프레임 워크에서 호출 됩니다.|  
|[CPane::OnAfterFloat](../Topic/CPane::OnAfterFloat.md)|창을 부동 되었습니다 때 프레임 워크에 의해 호출 됩니다.|  
|[CPane::OnBeforeDock](../Topic/CPane::OnBeforeDock.md)|창에 도킹 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)|창에 놓을지 약 할 때 프레임 워크에 의해 호출 됩니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPane::m\_bHandleMinSize](../Topic/CPane::m_bHandleMinSize.md)|창의 최소 크기를 일관성 있게 처리할 수 있습니다.|  
|[CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)|최근 도킹 정보가 들어 있습니다.|  
  
## 설명  
 일반적으로 `CPane` 개체 직접 인스턴스화할 수 있습니다.  창 도킹 기능 필요로 하는 경우 해당 개체에서 파생  [CDockablePane](../../mfc/reference/cdockablepane-class.md).  도구 모음 기능을 필요로 하는 경우 해당 개체에서 파생  [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 클래스에서 파생 `CPane`에 도킹 될 수 있는  [CDockSite](../../mfc/reference/cdocksite-class.md) 및에 나는  [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## 요구 사항  
 **헤더:** afxPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)