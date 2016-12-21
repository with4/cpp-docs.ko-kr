---
title: "CMFCBaseTabCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCBaseTabCtrl class"
ms.assetid: 7270c55f-6f6e-4dd2-b0d2-291afeac3882
caps.latest.revision: 41
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭 창의 기본 기능을 구현합니다.  
  
## 구문  
  
```  
class CMFCBaseTabCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCBaseTabCtrl::AddIcon](../Topic/CMFCBaseTabCtrl::AddIcon.md)||  
|[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md)|탭 창에 새 탭을 추가합니다.|  
|[CMFCBaseTabCtrl::ApplyRestoredTabInfo](../Topic/CMFCBaseTabCtrl::ApplyRestoredTabInfo.md)||  
|[CMFCBaseTabCtrl::AutoDestroyWindow](../Topic/CMFCBaseTabCtrl::AutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::CalcRectEdit](../Topic/CMFCBaseTabCtrl::CalcRectEdit.md)||  
|[CMFCBaseTabCtrl::CleanUp](../Topic/CMFCBaseTabCtrl::CleanUp.md)||  
|[CMFCBaseTabCtrl::ClearImageList](../Topic/CMFCBaseTabCtrl::ClearImageList.md)||  
|[CMFCBaseTabCtrl::DetachTab](../Topic/CMFCBaseTabCtrl::DetachTab.md)|탭 창에서 탭을 분리합니다.|  
|[CMFCBaseTabCtrl::EnableActivateLastActive](../Topic/CMFCBaseTabCtrl::EnableActivateLastActive.md)||  
|[CMFCBaseTabCtrl::EnableAutoColor](../Topic/CMFCBaseTabCtrl::EnableAutoColor.md)|탭 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCBaseTabCtrl::EnableCustomToolTips](../Topic/CMFCBaseTabCtrl::EnableCustomToolTips.md)|탭에 사용자 지정 도구 설명을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md)|탭 레이블 직접 편집을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md)|분리 가능한 탭을 사용하도록 설정합니다.|  
|[CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md)|사용자가 마우스를 사용해 탭 순서를 변경할 수 있도록 설정하거나 이를 해제합니다.|  
|[CMFCBaseTabCtrl::EnsureVisible](../Topic/CMFCBaseTabCtrl::EnsureVisible.md)|지정된 탭이 표시될 때까지 탭을 스크롤합니다. 이 메서드는 지정된 탭이 이미 표시되는 경우에는 효과가 없습니다.|  
|[CMFCBaseTabCtrl::EnterDragMode](../Topic/CMFCBaseTabCtrl::EnterDragMode.md)||  
|[CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md)|지정된 지점에 포함된 창을 반환합니다.|  
|[CMFCBaseTabCtrl::FireChangeActiveTab](../Topic/CMFCBaseTabCtrl::FireChangeActiveTab.md)||  
|[CMFCBaseTabCtrl::FireChangingActiveTab](../Topic/CMFCBaseTabCtrl::FireChangingActiveTab.md)||  
|[CMFCBaseTabCtrl::GetActiveTab](../Topic/CMFCBaseTabCtrl::GetActiveTab.md)|활성 탭의 인덱스를 반환합니다.|  
|[CMFCBaseTabCtrl::GetActiveTabColor](../Topic/CMFCBaseTabCtrl::GetActiveTabColor.md)|활성 탭의 배경색을 반환합니다.|  
|[CMFCBaseTabCtrl::GetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::GetActiveTabTextColor.md)|활성 탭의 텍스트 색을 반환합니다.|  
|[CMFCBaseTabCtrl::GetActiveWnd](../Topic/CMFCBaseTabCtrl::GetActiveWnd.md)|탭 컨트롤의 활성 페이지 포인터를 반환합니다.|  
|[CMFCBaseTabCtrl::GetAutoColors](../Topic/CMFCBaseTabCtrl::GetAutoColors.md)|자동 색 지정에 사용되는 색 배열에 대한 참조를 반환합니다.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTab](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTab.md)|첫 번째 표시 탭에 대한 포인터를 반환합니다.|  
|[CMFCBaseTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTabNum.md)||  
|[CMFCBaseTabCtrl::GetHighlightedTab](../Topic/CMFCBaseTabCtrl::GetHighlightedTab.md)|현재 강조 표시된 탭의 인덱스를 반환합니다.|  
|[CMFCBaseTabCtrl::GetImageList](../Topic/CMFCBaseTabCtrl::GetImageList.md)||  
|[CMFCBaseTabCtrl::GetImageSize](../Topic/CMFCBaseTabCtrl::GetImageSize.md)||  
|[CMFCBaseTabCtrl::GetLastVisibleTab](../Topic/CMFCBaseTabCtrl::GetLastVisibleTab.md)||  
|[CMFCBaseTabCtrl::GetLocation](../Topic/CMFCBaseTabCtrl::GetLocation.md)|탭 컨트롤을 기준으로 탭 영역이 배치되는 위치를 나타내는 LOCATION 데이터 형식의 변수를 반환합니다. 예를 들어 위쪽 또는 아래쪽에 있을 수 있습니다.|  
|[CMFCBaseTabCtrl::GetMaxWindowSize](../Topic/CMFCBaseTabCtrl::GetMaxWindowSize.md)||  
|[CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md)|탭 창에 있는 탭 영역의 크기와 위치를 반환합니다. 탭 영역의 위치는 좌표를 사용하여 정의됩니다.|  
|[CMFCBaseTabCtrl::GetTabBkColor](../Topic/CMFCBaseTabCtrl::GetTabBkColor.md)|지정된 탭의 배경색을 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabBorderSize](../Topic/CMFCBaseTabCtrl::GetTabBorderSize.md)|탭 컨트롤의 탭 테두리 크기를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabByID](../Topic/CMFCBaseTabCtrl::GetTabByID.md)|지정된 ID로 식별되는 탭 인덱스를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabCloseButton](../Topic/CMFCBaseTabCtrl::GetTabCloseButton.md)||  
|[CMFCBaseTabCtrl::GetTabFromHwnd](../Topic/CMFCBaseTabCtrl::GetTabFromHwnd.md)|지정된 HWND 개체가 포함된 탭의 인덱스를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md)|지정된 지점이 포함된 탭을 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabFullWidth](../Topic/CMFCBaseTabCtrl::GetTabFullWidth.md)||  
|[CMFCBaseTabCtrl::GetTabHicon](../Topic/CMFCBaseTabCtrl::GetTabHicon.md)|지정된 키와 연결된 아이콘을 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabID](../Topic/CMFCBaseTabCtrl::GetTabID.md)|탭의 인덱스를 사용하여 탭의 ID를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabIcon](../Topic/CMFCBaseTabCtrl::GetTabIcon.md)|지정된 탭에 대한 아이콘 ID를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabLabel](../Topic/CMFCBaseTabCtrl::GetTabLabel.md)|지정된 탭의 텍스트를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabRect](../Topic/CMFCBaseTabCtrl::GetTabRect.md)|지정된 탭의 크기와 위치를 검색합니다.|  
|[CMFCBaseTabCtrl::GetTabsHeight](../Topic/CMFCBaseTabCtrl::GetTabsHeight.md)||  
|[CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md)||  
|[CMFCBaseTabCtrl::GetTabTextColor](../Topic/CMFCBaseTabCtrl::GetTabTextColor.md)|지정된 탭의 텍스트 색을 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabWnd](../Topic/CMFCBaseTabCtrl::GetTabWnd.md)|지정된 탭 페이지에 있는 창에 대한 포인터를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabWndNoWrapper](../Topic/CMFCBaseTabCtrl::GetTabWndNoWrapper.md)|컨트롤에 래퍼가 있는 경우에도, 지정된 탭 페이지에 있는 컨트롤에 대한 직접 포인터를 반환합니다.|  
|[CMFCBaseTabCtrl::GetTabsNum](../Topic/CMFCBaseTabCtrl::GetTabsNum.md)|탭 컨트롤에 포함된 탭의 개수를 반환합니다.|  
|[CMFCBaseTabCtrl::GetToolTipCtrl](../Topic/CMFCBaseTabCtrl::GetToolTipCtrl.md)|`CMFCBaseTabCtrl` 개체와 연결된 도구 설명에 대한 참조를 반환합니다.|  
|[CMFCBaseTabCtrl::GetVisibleTabsNum](../Topic/CMFCBaseTabCtrl::GetVisibleTabsNum.md)|표시 탭의 개수를 반환합니다.|  
|[CMFCBaseTabCtrl::HasImage](../Topic/CMFCBaseTabCtrl::HasImage.md)||  
|[CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md)|탭 창을 숨기는 옵션을 설정합니다. 단, 탭 창이 표시 탭 하나만 표시하는 경우에 해당합니다.|  
|[CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md)|새 탭을 삽입합니다.|  
|[CMFCBaseTabCtrl::InvalidateTab](../Topic/CMFCBaseTabCtrl::InvalidateTab.md)||  
|[CMFCBaseTabCtrl::IsActiveTabCloseButton](../Topic/CMFCBaseTabCtrl::IsActiveTabCloseButton.md)||  
|[CMFCBaseTabCtrl::IsAutoColor](../Topic/CMFCBaseTabCtrl::IsAutoColor.md)|탭 창이 자동 색 모드인지 여부를 나타내는 값을 반환합니다.|  
|[CMFCBaseTabCtrl::IsAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::IsAutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::IsColored](../Topic/CMFCBaseTabCtrl::IsColored.md)||  
|[CMFCBaseTabCtrl::IsDialogControl](../Topic/CMFCBaseTabCtrl::IsDialogControl.md)||  
|[CMFCBaseTabCtrl::IsDrawNoPrefix](../Topic/CMFCBaseTabCtrl::IsDrawNoPrefix.md)||  
|[CMFCBaseTabCtrl::IsFlatFrame](../Topic/CMFCBaseTabCtrl::IsFlatFrame.md)|탭 영역의 프레임이 평면인지 아니면 3D인지를 나타내는 값을 반환합니다.|  
|[CMFCBaseTabCtrl::IsFlatTab](../Topic/CMFCBaseTabCtrl::IsFlatTab.md)||  
|[CMFCBaseTabCtrl::IsHideSingleTab](../Topic/CMFCBaseTabCtrl::IsHideSingleTab.md)|탭 컨트롤이 탭을 숨기도록 구성되어 있는지 여부를 나타내는 값을 반환합니다. 단, 탭 창에 표시 탭 하나만 있는 경우에 해당합니다.|  
|[CMFCBaseTabCtrl::IsIconAdded](../Topic/CMFCBaseTabCtrl::IsIconAdded.md)||  
|[CMFCBaseTabCtrl::IsInPlaceEdit](../Topic/CMFCBaseTabCtrl::IsInPlaceEdit.md)|사용자가 탭의 레이블을 수정할 수 있는지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsLeftRightRounded](../Topic/CMFCBaseTabCtrl::IsLeftRightRounded.md)||  
|[CMFCBaseTabCtrl::IsMDITab](../Topic/CMFCBaseTabCtrl::IsMDITab.md)||  
|[CMFCBaseTabCtrl::IsOneNoteStyle](../Topic/CMFCBaseTabCtrl::IsOneNoteStyle.md)|탭 창에 Microsoft OneNote 스타일의 탭이 표시되는지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md)|지정된 지점이 탭 영역에 있는지 여부를 확인합니다.|  
|[CMFCBaseTabCtrl::IsTabCloseButtonHighlighted](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonHighlighted.md)||  
|[CMFCBaseTabCtrl::IsTabCloseButtonPressed](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonPressed.md)||  
|[CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md)|탭이 분리 가능한지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsTabIconOnly](../Topic/CMFCBaseTabCtrl::IsTabIconOnly.md)|탭에 레이블 대신 아이콘이 표시되는지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsTabSwapEnabled](../Topic/CMFCBaseTabCtrl::IsTabSwapEnabled.md)|사용자가 탭을 끌어 탭 위치를 변경할 수 있는지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsTabVisible](../Topic/CMFCBaseTabCtrl::IsTabVisible.md)|지정된 탭이 표시되는지 여부를 나타냅니다.|  
|[CMFCBaseTabCtrl::IsVS2005Style](../Topic/CMFCBaseTabCtrl::IsVS2005Style.md)||  
|[CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md)||  
|[CMFCBaseTabCtrl::OnChangeTabs](../Topic/CMFCBaseTabCtrl::OnChangeTabs.md)|탭 개수가 변경되면 프레임워크에서 호출합니다.|  
|[CMFCBaseTabCtrl::OnDragEnter](../Topic/CMFCBaseTabCtrl::OnDragEnter.md)||  
|[CMFCBaseTabCtrl::OnDragLeave](../Topic/CMFCBaseTabCtrl::OnDragLeave.md)||  
|[CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md)||  
|[CMFCBaseTabCtrl::OnDrop](../Topic/CMFCBaseTabCtrl::OnDrop.md)||  
|[CMFCBaseTabCtrl::OnRenameTab](../Topic/CMFCBaseTabCtrl::OnRenameTab.md)||  
|[CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md)|창 메시지가 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수로 디스패치되기 전에 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스가 이 메시지를 해석하는 데 사용됩니다. \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)를 재정의합니다.\)|  
|[CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md)|탭 창의 내부 레이아웃을 다시 계산합니다.|  
|[CMFCBaseTabCtrl::RemoveAllTabs](../Topic/CMFCBaseTabCtrl::RemoveAllTabs.md)|탭 창에서 모든 탭을 제거합니다.|  
|[CMFCBaseTabCtrl::RemoveTab](../Topic/CMFCBaseTabCtrl::RemoveTab.md)|탭 창에서 탭을 제거합니다.|  
|[CMFCBaseTabCtrl::RenameTab](../Topic/CMFCBaseTabCtrl::RenameTab.md)||  
|[CMFCBaseTabCtrl::ResetImageList](../Topic/CMFCBaseTabCtrl::ResetImageList.md)|탭 창에 연결된 이미지 목록을 다시 설정합니다.|  
|[CMFCBaseTabCtrl::Serialize](../Topic/CMFCBaseTabCtrl::Serialize.md)|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. \([CObject::Serialize](../Topic/CObject::Serialize.md)를 재정의합니다.\)|  
|[CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md)|탭을 활성화합니다.|  
|[CMFCBaseTabCtrl::SetActiveTabColor](../Topic/CMFCBaseTabCtrl::SetActiveTabColor.md)|현재 활성 탭의 배경색을 설정합니다.|  
|[CMFCBaseTabCtrl::SetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::SetActiveTabTextColor.md)|활성 탭의 텍스트 색을 설정합니다.|  
|[CMFCBaseTabCtrl::SetAutoColors](../Topic/CMFCBaseTabCtrl::SetAutoColors.md)|자동 색 모드에서 적용되는 탭 컨트롤 색을 설정합니다.|  
|[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)|[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)에서 파생되지 않은 개체에 사용되는 래퍼 클래스를 설정합니다.|  
|[CMFCBaseTabCtrl::SetDrawNoPrefix](../Topic/CMFCBaseTabCtrl::SetDrawNoPrefix.md)|레이블이 그려질 때 접두사 처리를 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md)|아이콘 이미지 목록을 설정합니다.|  
|[CMFCBaseTabCtrl::SetLocation](../Topic/CMFCBaseTabCtrl::SetLocation.md)||  
|[CMFCBaseTabCtrl::SetTabBkColor](../Topic/CMFCBaseTabCtrl::SetTabBkColor.md)|지정된 탭의 배경색을 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabBorderSize](../Topic/CMFCBaseTabCtrl::SetTabBorderSize.md)|새 탭 테두리 크기를 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabHicon](../Topic/CMFCBaseTabCtrl::SetTabHicon.md)|탭 아이콘을 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabIcon](../Topic/CMFCBaseTabCtrl::SetTabIcon.md)|탭 아이콘 ID를 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabIconOnly](../Topic/CMFCBaseTabCtrl::SetTabIconOnly.md)|지정된 탭에 대해 "아이콘만" 모드를 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabLabel](../Topic/CMFCBaseTabCtrl::SetTabLabel.md)|탭 레이블을 지정 문자열 값과 같도록 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabsHeight](../Topic/CMFCBaseTabCtrl::SetTabsHeight.md)||  
|[CMFCBaseTabCtrl::SetTabTextColor](../Topic/CMFCBaseTabCtrl::SetTabTextColor.md)|지정된 탭의 텍스트 색을 설정합니다.|  
|[CMFCBaseTabCtrl::SetTabsOrder](../Topic/CMFCBaseTabCtrl::SetTabsOrder.md)|지정된 순서대로 탭을 정렬합니다.|  
|[CMFCBaseTabCtrl::ShowTab](../Topic/CMFCBaseTabCtrl::ShowTab.md)|지정된 탭을 표시하거나 숨깁니다.|  
|[CMFCBaseTabCtrl::StartRenameTab](../Topic/CMFCBaseTabCtrl::StartRenameTab.md)||  
|[CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md)||  
  
### 보호된 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCBaseTabCtrl::CreateWrapper](../Topic/CMFCBaseTabCtrl::CreateWrapper.md)|`CDockablePane`에서 파생되지 않은 [CWnd](../../mfc/reference/cwnd-class.md)에서 파생된 개체에 대한 래퍼를 만듭니다.`CMFCBaseTabCtrl` 개체를 도킹하려면 포함된 모든 컨트롤이`CDockablePane`에서 파생되었거나 이 컨트롤에 도킹 래퍼가 있어야 합니다.<br /><br /> `SetDockingBayWrapperRTC`를 사용하여 래퍼의 클래스를 설정합니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCBaseTabCtrl::m\_bActivateTabOnRightClick](../Topic/CMFCBaseTabCtrl::m_bActivateTabOnRightClick.md)|마우스 왼쪽 단추 클릭이나 마우스 오른쪽 단추 클릭 중 어느 것을 사용하여 탭을 선택할지를 지정합니다.|  
|[CMFCBaseTabCtrl::m\_bAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::m_bAutoDestroyWindow.md)|탭에 포함된 창이 자동으로 소멸되는지 여부를 지정합니다.|  
  
## 설명  
 `CMFCBaseTabCtrl` 클래스는 추상 클래스입니다. 따라서 인스턴스화할 수 없습니다. 탭 창을 만들려면 `CMFCBaseTabCtrl`에서 클래스를 파생해야 합니다. MFC 라이브러리에는 몇 가지 파생 클래스 예제가 있으며, 그중 두 개는 [CMFCTabCtrl Class](../../mfc/reference/cmfctabctrl-class.md) 및 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)입니다.  
  
 [!INCLUDE[vs_dev14](../../ide/includes/vs_dev14_md.md)]부터 이 클래스는 Microsoft Active Accessibility를 지원합니다.  
  
## 사용자 지정 팁  
 다음은 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) 및 이 클래스에서 상속되는 클래스와 관련된 팁입니다.  
  
-   분리 가능한 탭을 사용하도록 설정하는 경우 탭 창에 대한 포인터를 유지하지 마세요. 이러한 분리 가능한 탭은 동적으로 만들고 제거할 수 있습니다. 따라서 포인터가 유효하지 않게 될 수 있습니다.  
  
-   사용자가 마우스를 사용해 탭 컨트롤에서 동적으로 탭을 이동할 수 있도록 탭 컨트롤을 구성할 수 있습니다. 이 기능은 `CMFCBaseTabCtrl` 클래스에서 기본으로 제공됩니다. 이 기능을 사용하려면 [CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md)을 호출합니다.  
  
-   탭 컨트롤에 탭을 추가하면 기본적으로 이 탭은 분리 가능한 상태입니다.[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md)을 사용하여 분리 불가능한 탭을 추가할 수도 있습니다. 매개 변수 `bDetachable`을 `FALSE`로 설정하는 경우 탭을 분리할 수 없습니다.[CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md) 메서드를 호출하여 탭의 분리 가능 여부를 변경할 수도 있습니다.  
  
-   [CWnd 클래스](../../mfc/reference/cwnd-class.md)에서 파생되는 개체를 도킹 가능한 컨트롤 막대나 도킹 가능한 탭에 배치할 수 있습니다. 전체 컨트롤을 도킹하려면 `CWnd` 개체를 도킹 가능하도록 만들어야 합니다. 이를 위해 MFC는 래퍼 클래스를 사용합니다. 이 래퍼 클래스는 [CDockablePaneAdapter Class](../../mfc/reference/cdockablepaneadapter-class.md)입니다. 도킹 가능한 컨트롤 막대나 도킹 가능한 탭에 추가되는 `CWnd` 개체는 `CDockablePaneAdapter` 개체 내에 래핑됩니다.`CMFCBaseTablCtrl` 개체의 매개 변수 `m_bEnableWrapping`을 `FALSE`로 설정하여 자동 래핑을 사용하지 않도록 설정할 수 있습니다.[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md) 메서드를 사용하여 응용 프로그램에서 래퍼로 사용할 클래스를 변경할 수도 있습니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxbasetabctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl Class](../../mfc/reference/cmfctabctrl-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)